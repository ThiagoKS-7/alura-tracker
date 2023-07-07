<template>
    <article class="panel is-info panel-container">
    <p class="panel-heading">
        {{ title }}
    </p>
    <template v-if="list && list?.length > 0">
        <a class="panel-block panel-item is-flex is-justify-content-center" v-for="item in list" :key="item.name+item.timeSpent">
            <span class="panel-icon">
                <i class="fas fa-book" aria-hidden="true"></i>
            </span>
            <span  class="mx-3">
                <strong>{{item.name}}</strong>
            </span>
            <span class="time-spent">
                <i class="fas fa-clock" aria-hidden="true"></i>
                {{item.timeSpent}}
            </span>
        </a>
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
import ITask from "@/types/ITask";


export default defineComponent({
    name: 'DefaultPanel',
    props: {
        title: { type: String, required: true },
        list:  { type: Array as PropType<ITask[]>, required: true },
    },
    setup(props) {
        props.title,
        props.list
    }
});
</script>

<style scoped>
@import "./style.css";
</style>