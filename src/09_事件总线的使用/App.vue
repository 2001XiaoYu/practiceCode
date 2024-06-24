<template>
    <div class="app">
        <h2>App Message: {{ message }}</h2>
        <home></home>
        <button @click="isShowCategory = false">是否显示category</button>
        <category v-if="isShowCategory"></category>
    </div>
</template>

<script>
import Category from './Category.vue';
import eventBus from './utils/event-bus.js'
import Home from './Home'
export default {
    components: {
        Home,
        Category
    },
    data() {
        return {
            message: "Hello App",
            isShowCategory: true
        }
    },
    created() {
        //fetch()

        //事件监听
        eventBus.on("whyEvent", (name, age, height) => {
            console.log("whyEvent事件在App中的监听", name, age, height);
            this.message = `name:${name}, age:${age}, height:${height}`
        })
    }
}
</script>

<style scoped></style>