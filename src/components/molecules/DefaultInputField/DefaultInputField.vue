<template>
    <div>

        <input 
            :class="class" 
            :type="type" 
            :placeholder="placeholder"
            :value="modelValue"
            @input="$event=> updateModelValue($event)"
        >
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'DefaultInputField',
    emits: ['change'],
    props: {
        type: { type: String, required: true },
        placeholder: { type: String, required: true },
        modelValue: { type: String, required: true },
        class: {
            type: String,
            default: "input is-normal is-info"
        }
    },
    setup(props) {
        props.type,
        props.placeholder
    },
    methods: {
        updateModelValue(evt:any) : void {
            if(evt.target) this.$emit('change', evt.target.value);
        }   
    }
});
</script>

<style scoped>
@import "./style.css";
</style>