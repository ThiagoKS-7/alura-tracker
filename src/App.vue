<template>
  <MainView />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MainView from '@/components/views/MainView.vue';

export default defineComponent({
  name: 'App',
  components: {
    MainView,
  }
});
</script>
