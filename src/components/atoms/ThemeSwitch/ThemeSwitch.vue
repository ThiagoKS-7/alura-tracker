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
        <label v-if="!checked"  for="themeSwitch" class="sun-icon">
            <span>
                <i  class="fa-regular fa-sun "></i>
            </span>
        </label>
        <label v-if="checked"  for="themeSwitch" class="moon-icon" tabindex="-1">
            <span>
                <i   class="fa-sharp fa-regular fa-moon"></i>
            </span>
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