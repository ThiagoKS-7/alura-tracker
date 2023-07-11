<template>
    <div class="info-wrapper">
        <section class="timer">
            <strong>{{timeStamp}}</strong>
        </section>
        <button :class="{
            'button action-btn': isDark == false,
            'button action-btn dark': isDark == true,
            }" 
            @click="onInit()" 
            :disabled="timeStamp !== '00:00:00'">
            <span class="icon has-text-success">
                <i class="fas fa-play"></i>
            </span>
            <span>play</span>
        </button>
        <button :class="{
            'button action-btn': isDark == false,
            'button action-btn dark': isDark == true,
            }"
            @click="onFinish()" 
            :disabled="timeStamp == '00:00:00' || !timeStamp">
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
        isDark: { type: Boolean, required: true},
        timeStamp: { type: String, required: true }, 
        onInit: { type: Function, required: true },
        onFinish: { type: Function, required: true },
    },
    setup(props) {
        props.isDark,
        props.timeStamp,
        props.onInit,
        props.onFinish
    }
});
</script>

<style scoped>
@import "./style.css";
</style>