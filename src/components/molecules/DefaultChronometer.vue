<template>
    <div class="info-wrapper">
        <section clas="timer">
            <string>{{timeStamp}}</string>
        </section>
        <button class="button action-btn" @click="onInit">
            <span class="icon has-text-success">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button class="button action-btn" @click="onFinish">
            <span class="icon has-text-danger">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
        </button>
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import type { PropType } from 'vue'
export default defineComponent({
    name: 'DefaultChronometer',
    props: {
        timeStamp: String, 
        onInit: Function,
        onFinish: Function,
    },
    setup(props) {
        props.timeStamp,
        props.onInit,
        props.onFinish
    }
});
</script>

<style>
</style>