<template>
    <div>
        <ThemeSwitch 
            :checked="darkIsSet"
            @update:checked="()=>updateChecked()"
        />
        <main  class="columns is-gapless is-multiline">
            <div class="column is-one-quarter">
                <DefaultSidebar/>
            </div>
            <div class="column is-three-quarter">
                <DefaultForm
                    :timer="chron.timer"
                    :timeStamp="timeStamp"
                    :taskValue="form.taskValue"
                    :onInit="()=>init()"
                    :isDark="darkIsSet"
                    :onFinish="()=>finish()"
                    @onChangeTaskVal="newValue => form.taskValue = newValue"
                />
                <div class="wrapper">
                    <DefaultPanel
                        title="Task History"
                        :isDark="darkIsSet"
                        :list="form.taskList"
                    />
                </div>
                {{ darkIsSet }}
            </div>
        </main>
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import DefaultSidebar from '@/components/molecules/DefaultSidebar/DefaultSidebar.vue';
import DefaultPanel from '@/components/organisms/DefaultPanel/DefaultPanel.vue';
import DefaultForm from '@/components/organisms/DefaultForm/DefaultForm.vue';
import ThemeSwitch from '@/components/atoms/ThemeSwitch/ThemeSwitch.vue';
import ITask from "@/types/ITask";



export default defineComponent({
    name: 'MainView',
    components: {
        DefaultSidebar,
        DefaultForm,
        DefaultPanel,
        ThemeSwitch
    },
    data() {
        return {
            darkIsSet: false,
            chron: {
                timeInSeconds: 0,
                timer: 0,
            },
            form: {
                taskList: [] as ITask[],
                taskValue: '',
            }
        }
    },
    computed: {
        timeStamp() : string {
            return new Date(this.chron.timeInSeconds*1000).toISOString().substr(11,8);
        },
    },
    methods: {
        init() : void {
            this.chron.timer = setInterval(()=> this.chron.timeInSeconds +=1, 1000);
        },
        finish() : void {
            this.form.taskList.push({name: this.form.taskValue, timeSpent: this.timeStamp})
            clearInterval(this.chron.timer);
            this.chron.timeInSeconds = 0;
        },
        updateChecked() {
            const body = document.body;
            const panelItems =  document.querySelectorAll<HTMLElement>('.panel-item');
            const content =  document.querySelectorAll<HTMLElement>('.is-three-quarter');
            const boxes =  document.querySelectorAll<HTMLElement>('.box');
            const inputs =  document.querySelectorAll<HTMLElement>('input');
            const buttons = document.querySelectorAll<HTMLElement>('.action-btn');
            const elements = [
                body,
                content,
                panelItems,
                boxes,
                inputs,
                buttons,
            ]
            this.darkIsSet = !this.darkIsSet;
            elements.forEach(el => {
                if (el instanceof NodeList) {
                    el.forEach(item => {
                        item.classList.toggle("dark")
                    });
                } else {
                    el.classList.toggle("dark")
                }
            })
        }
    }
});
</script>

<style>
.wrapper {
    display: flex;
    justify-content: center;
}
</style>