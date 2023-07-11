<template>
    <div class="input-container">
        <label class="is-size-5" for="input" v-if="label">
            {{ label }}
        </label>
        <input 
            id="input"
            name="input"
            :class="{
                'input is-info': className == 'default' && isDark == false,
                'input is-info dark': isDark == true
            }" 
            :type="type" 
            :placeholder="placeholder"
            :value="modelValue"
            @input="event=> updateModelValue(event)">
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'DefaultInputField',
    emits: ['change'],
    props: {
        label: { type: String },
        isDark: { type: Boolean, required: true },
        type: { type: String, required: true },
        placeholder: { type: String, required: true },
        modelValue: { type: String, required: true },
        className: {
            type: String,
            default: "default"
        }
    },
    setup(props) {
        props.label,
        props.isDark,
        props.className,
        props.modelValue,
        props.type,
        props.placeholder
    },
    methods: {
        updateModelValue(evt:any) : void {
            if(evt.target)  this.$emit('change', evt.target.value);
        }   
    }
});
</script>

<style scoped>
@import "./style.css";
</style>