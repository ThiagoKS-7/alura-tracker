<template>
    <header>
        <BrandDefault/>
    </header>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import BrandDefault from '../atoms/BrandDefault.vue'; 

export default defineComponent({
    name: 'DefaultSidebar',
    components: {
        BrandDefault
    }
});
</script>

<style  scoped>
header {
    padding: 1rem;
    background: #0d3b66;
    width: 100%;
    height: 100vh;
}
@media only screen and (max-width: 768px) {
    header {
        padding: 2.5rem;
        align-self: center;
        height: auto;
        display: flex;
        justify-content: center;
    }
}
</style>