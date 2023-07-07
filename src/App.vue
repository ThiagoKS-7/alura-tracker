<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <DefaultSidebar/>
    </div>
    <div class="column is-three-quarter">
      <DefaultForm/>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import DefaultSidebar from './components/DefaultSideBar.vue';
import DefaultForm from './components/DefaultForm.vue';

export default defineComponent({
  name: 'App',
  components: {
    DefaultSidebar,
    DefaultForm,
  }
});
</script>

<style>

</style>