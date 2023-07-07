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
            <strong class="mx-3">{{item.name}}</strong>  - 
            <span class="mx-3">
                <i class="fas fa-clock" aria-hidden="true"></i>
                {{item.timeSpent}}
            </span>
        </a>
    </template>
    <template v-else>
        <a class="panel-block is-flex is-justify-content-center">
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

interface Task {
    name: string;
    timeSpent: string;
}

export default defineComponent({
    name: 'DefaultPanel',
    props: {
        title: String,
        list: [] as Task[]
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