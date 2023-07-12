<template>
    <header>
        <div class="sidebar-container">
            <BrandDefault/>
            <div class="theme-container">
                <ThemeSwitch 
                    :checked="isDark"
                    @update:checked="(event) => $emit('update:checked', event)"
                />
            </div>
            <span class="bars-icon" @click="showDropdown()">
                <i class="fa-solid fa-bars"></i>
                <div class="is-hidden">
                    <ul>
                        <li class="is-flex is-justify-content-space-around">
                            <span>Theme: </span>
                            <ThemeSwitch 
                                :checked="isDark"
                                @update:checked="(event) => $emit('update:checked', event)"
                            />
                        </li>
                    </ul>
                </div>
            </span>
        </div>
    </header>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import BrandDefault from '@/components/atoms/BrandDefault/BrandDefault.vue'; 
import ThemeSwitch from '@/components/atoms/ThemeSwitch/ThemeSwitch.vue';

export default defineComponent({
    name: 'DefaultSidebar',
    components: {
        ThemeSwitch,
        BrandDefault
    },
    props: {
        isDark: { type: Boolean,required:true}
    },
    setup(props) {
        props.isDark
    },
    methods: {
        showDropdown() {
            const dropdowns = document.querySelectorAll<HTMLElement>('.is-hidden');
            dropdowns.forEach(el => {
                if (this.isDark) {
                    el.classList.toggle('bars-dropdown');
                    el.classList.add('dark');
                } else {
                    el.classList.remove('dark');
                    el.classList.toggle('bars-dropdown');
                }
            })

        }
    }
});
</script>

<style scoped>
@import "./style.css";
</style>