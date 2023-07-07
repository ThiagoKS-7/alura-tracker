<template>
    <input 
        class="input" 
        :type="type" 
        :placeholder="placeholder"
        :value="modelValue"
        @input="$emit('change', $event.target.value)"
    >
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'DefaultInputField',
    emits: ['change'],
    props: {
        type: String,
        placeholder: String,
        modelValue: String,
    },
    setup(props) {
        props.type,
        props.placeholder
    },
});
</script>

<style scoped>
@import "./style.css";
</style>