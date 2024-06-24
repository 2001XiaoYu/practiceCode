<template>
    <div class="app">
        <div class="tabs">
            <template v-for="(item, index) in tabs" :key="item">
                <button :class="{ active: currentIndex === index }" 
                @click="itemClick(index)">{{ item }}</button>
            </template>
        </div>
        <div class="view">
            <!-- 1.第一种做法: v-if 进行逻辑判断，决定显示不同的组件 -->
             <!-- <template v-if="currentIndex === 0">
                <home></home>
             </template>
             <template v-else-if="currentIndex === 1">
                <about></about>
             </template>
             <template v-else-if="currentIndex === 2">
                <category></category>
             </template> -->

             <!-- 2.第二种做法：动态组件 component -->
              <!-- is中的组件需要来自两个地方：1.全局注册的组件  2.局部注册的组件 -->
              <component name="why" :age="18" @homeClick="homeClick" :is="tabs[currentIndex]"></component>
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