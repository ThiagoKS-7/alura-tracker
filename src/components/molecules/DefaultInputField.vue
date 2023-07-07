<template>
    <div 
        class="column is-8 input-wrapper" 
        role="form" 
        aria-label="Formulário de criação de tarefas"
    >
        <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?">
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'DefaultInputField',


});
</script>

<style>
</style>