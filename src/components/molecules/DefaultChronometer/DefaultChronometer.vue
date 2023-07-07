<template>
    <div class="info-wrapper">
        <section clas="timer">
            <strong>{{timeStamp}}</strong>
        </section>
        <button class="button action-btn" @click="onInit" :disabled="timeStamp !== '00:00:00'">
            <span class="icon has-text-success">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button class="button action-btn" @click="onFinish" :disabled="timeStamp == '00:00:00' || !timeStamp">
            <span class="icon has-text-danger">
                <i class="fas fa-stop"></i>
            </span>
            <span>stop</span>
        </button>
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

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

<style scoped>
@import "./style.css";
</style>