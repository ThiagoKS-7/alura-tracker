<template>
    <header>
        <BrandDefault/>
    </header>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import BrandDefault from '@/components/atoms/BrandDefault/BrandDefault.vue'; 

export default defineComponent({
    name: 'DefaultSidebar',
    components: {
        BrandDefault
    }
});
</script>

<style scoped>
@import "./style.css";
</style>