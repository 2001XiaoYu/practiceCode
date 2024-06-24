<template>
    <div class="app">
        <!-- 1.input v-model -->
        <!-- <input v-model="message">
        <input :value="message" @input="message = $event.target.value"> -->

        <!-- 2.组件的v-model :默认modelValue -->
        <!-- <counter v-model="appCounter"></counter> -->
        <!-- 这行注释的上下两行代码的作用是一致的 -->
        <!-- <counter :modelValue="appCounter" @update:modelValue="appCounter = $event"></counter> -->

        <!-- 3.组件的v-model：自定义名称 -->
         <counter2 v-model:counter="appCounter" v-model:why="appWhy"></counter2>
    </div>
</template>

<script>
import Counter from './Counter.vue'
import Counter2 from './Counter2.vue'
export default {
    components: {
        Counter,
        Counter2
    },
    data() {
        return {
            message: "Hello nie",
            appCounter: 100,
            appWhy: "nieyubo"
        }
    }
}
</script>

<style scoped>
.app {
    font-size: 20px;
}
</style>