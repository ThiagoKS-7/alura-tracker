<template>
    <a class="panel-block panel-item is-flex is-justify-content-center">
            <span class="panel-icon">
                <i class="fas fa-book" aria-hidden="true"></i>
            </span>
            <span  class="desc">
                <strong>{{name || "Tarefa sem descrição"}}</strong>
            </span>
            <span class="time-spent">
                <i class="fas fa-clock" aria-hidden="true"></i>
                {{timeSpent}}
            </span>
        </a>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'PanelItem',
    props: {
        name: { type: String, required: true },
        timeSpent: { type: String, required: true },
    }
});
</script>

<style scoped>
@import "./style.css";
</style>