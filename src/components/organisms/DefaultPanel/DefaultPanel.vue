<template>
    <article class="panel is-info panel-container">
    <p class="panel-heading">
        {{ title }}
    </p>
    <template v-if="list && list?.length > 0">
        <PanelItem 
            v-for="(item,index) in list" 
            :key="index" 
            :name="item.name"
            :timeSpent="item.timeSpent"
        />
    </template>
    <template v-else>
        <a class="panel-block panel-item is-flex is-justify-content-center">
            <span class="panel-icon">
            <i class="fas fa-book" aria-hidden="true"></i>
            </span>
            <strong>Dados indisponíveis</strong>
        </a>
    </template>
</article>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import { PropType } from 'vue';
import PanelItem from '@/components/atoms/PanelItem/PanelItem.vue';
import ITask from "@/types/ITask";


export default defineComponent({
    name: "DefaultPanel",
    props: {
        title: { type: String, required: true },
        list: { type: Array as PropType<ITask[]>, required: true },
    },
    setup(props) {
        props.title,
            props.list;
    },
    components: { PanelItem }
});
</script>

<style scoped>
@import "./style.css";
</style>