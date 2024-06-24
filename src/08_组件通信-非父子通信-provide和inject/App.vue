<template>
    <div class="app">
        <home></home>
        <h2>{{ message }}</h2>
        <button @click="message = '你好，app'">修改message</button>
    </div>
</template>

<script>
import { computed } from 'vue'
import Home from './Home'
export default {
    components: {
        Home
    },
    data() {
        return {
            message: "Hello App"
        }
    },
    //provide一般都是写成函数
    provide() {
        return {
            name: "nie",
            age: 18,
            message: computed(() => this.message)
        }
    }
}
</script>

<style scoped></style>