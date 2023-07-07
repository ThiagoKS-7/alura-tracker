<template>
    <main class="columns is-gapless is-multiline">
        <div class="column is-one-quarter">
            <DefaultSidebar/>
        </div>
        <div class="column is-three-quarter">
            <DefaultForm
                :timer="timer"
                :timeStamp="timeStamp"
                :onInit="()=>init()"
                :onFinish="()=>finish()"
            />
        </div>
    </main>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import DefaultSidebar from '../molecules/DefaultSideBar.vue';
import DefaultForm from '../organisms/DefaultForm.vue';

export default defineComponent({
    name: 'MainView',
    components: {
        DefaultSidebar,
        DefaultForm,
    },
    data() {
        return {
            timeInSeconds: 0,
            timer: 0,
        }
    },
    computed: {
        timeStamp() : string {
            return new Date(this.timeInSeconds*1000).toISOString().substr(11,8);
        },
    },
    methods: {
        init() {
            this.timer = setInterval(()=> this.timeInSeconds +=1, 1000);
        },
        finish() {
            clearInterval(this.timer);
            this.timeInSeconds = 0;
            
        },
    }
});
</script>

<style>
</style>