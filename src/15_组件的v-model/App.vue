<template>
    <div class="app">
        <!-- 1.input v-model -->
        <!-- <input v-model="message">
        <input :value="message" @input="message = $event.target.value"> -->

        <!-- 2.组件的v-model -->
         <counter v-model="appCounter"></counter>
         <!-- 这行注释的上下两行代码的作用是一致的 -->
         <!-- <counter :modelValue="appCounter" @update:modelValue="appCounter = $event"></counter> -->
    </div>
</template>

<script>
import Counter from './Counter.vue'
    export default {
        components: {
            Counter
        },
        data() {
            return {
                message: "Hello nie",
                appCounter: 100
            }
        }
    }
</script>

<style scoped>
</style>