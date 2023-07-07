<template>
    <div class="box">
        <div class="columns">
            <div class="column">
                <DefaultChronometer
                    :timeStamp="timeStamp"
                    :onInit="onInit"
                    :onFinish="onFinish"
                />
            </div>
        </div>
    </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import DefaultChronometer from '../molecules/DefaultChronometer.vue';

export default defineComponent({
    name: 'DefaultForm',
    components:  {
        DefaultChronometer
    },
    props: {
        timer: Number,
        timeStamp: String, 
        onInit: Function,
        onFinish: Function,
    },
    setup(props) {
        props.timer,
        props.timeStamp,
        props.onInit,
        props.onFinish
    }
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