<template>
    <div>
        <input 
            type="checkbox" 
            id="themeSwitch" 
            name="theme-switch" 
            class="theme-switch__input"
            :checked="checked"
            @input="(event) => $emit('update:checked', event.target.checked)"
        />
        <label for="themeSwitch" class="theme-switch__label">
            <span>Switch Theme</span>
        </label>
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'ThemeSwitch',
    props: {
        checked: { type: Boolean, required: true}
    },
    setup(props) {
        props.checked
    }
});
</script>

<style>
@import './style.css';
</style>