<template>
    <div id="form" class="box">
        <div class="columns">
            <form 
                class="column is-8 input-wrapper" 
                aria-label="Formulário de criação de tarefas"
            >
                <DefaultInputField
                    type="text" 
                    label="Task Name"
                    placeholder="Ex: React"
                    :modelValue="taskValue"
                    :isDark="isDark"
                    @change="$emit('onChangeTaskVal', $event)"
                />
            </form>
            <div class="column">
                <DefaultChronometer
                    :timeStamp="timeStamp"
                    :onInit="onInit"
                    :isDark="isDark"
                    :onFinish="onFinish"
                />
            </div>
        </div>
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import DefaultInputField from '@/components/molecules/DefaultInputField/DefaultInputField.vue';
import DefaultChronometer from '@/components/molecules/DefaultChronometer/DefaultChronometer.vue';

export default defineComponent({
    name: 'DefaultForm',
    components:  {
        DefaultChronometer,
        DefaultInputField
    },
    emits: ['onChangeTaskVal'],
    props: {
        taskValue: { type: String, required: true },
        isDark: { type: Boolean, required: true },
        timer: { type: Number, required: true },
        timeStamp:{ type: String, required: true }, 
        onInit: { type: Function, required: true },
        onFinish: { type: Function, required: true },
    },
    setup(props) {
        props.taskValue,
        props.timer,
        props.isDark,
        props.timeStamp,
        props.onInit,
        props.onFinish
    },
});
</script>

<style scoped>
@import "./style.css";
</style>    