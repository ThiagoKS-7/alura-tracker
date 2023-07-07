<template>
    <div class="box">
        <div class="columns">
            <div 
                class="column is-8 input-wrapper" 
                role="form" 
                aria-label="Formulário de criação de tarefas"
            >
                <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?">
            </div>
            <div class="column">
                <div class="info-wrapper">
                    <section clas="timer">
                        <string>00:00:00</string>
                    </section>
                    <button class="button action-btn">
                        <span class="icon has-text-success">
                            <i class="fas fa-play"></i>
                        </span>
                        <span>play</span>
                    </button>
                    <button class="button action-btn">
                        <span class="icon has-text-danger">
                            <i class="fas fa-stop"></i>
                        </span>
                        <span>stop</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';

export default defineComponent({
name: 'DefaultForm'
});
</script>

<style>
.info-wrapper {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
}
.action-btn {
    margin: 0.5rem 0;
    min-width: 8vw;
}
.input-wrapper {
    display: flex;
    align-items: center;
}


@media only screen and (max-width: 370px) {
    .action-btn {
        margin: 0;
        min-width: 85px;
    }
}
@media only screen  and (min-width: 371px) and (max-width: 768px) {
    .action-btn {
        margin: 0 0.5rem;
        min-width: 33vw;
    }
}
@media only screen and (min-width: 769px)  and (max-width: 1279px) {
    .action-btn {
        margin: 0.5rem 0;
        width: 100%;
    }
    .info-wrapper {
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        flex-flow: column;
    }
    .input-wrapper {
        display: initial;
        align-items: center;
    }

}
</style>