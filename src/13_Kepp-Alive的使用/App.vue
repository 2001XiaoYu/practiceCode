<template>
    <div class="app">
        <div class="tabs">
            <template v-for="(item, index) in tabs" :key="item">
                <button :class="{ active: currentIndex === index }" 
                @click="itemClick(index)">{{ item }}</button>
            </template>
        </div>
        <div class="view">
            <!-- include: 组件的名称来自于组件定义时name选项 -->
            <keep-alive include="home,about">
                <component :is="tabs[currentIndex]"></component>
            </keep-alive>
        </div>
    </div>
</template>

<script>
import Home from './views/Home'
import About from './views/About'
import Category from './views/Category'

    export default {
        components: {
            Home,
            About,
            Category
        },
        data() {
            return {
                tabs: ["home", "about", "category"],
                currentIndex: 0
            }
        },
        methods: {
            itemClick(index) {
                this.currentIndex = index
            },
            homeClick(arg) {
                console.log("homeClick:", arg);
            }
        }
    }
</script>

<style scoped>
.active {
    color: red;
}
</style>