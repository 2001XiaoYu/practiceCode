<template>
    <div class="app">
        <!-- 1.tab-control -->
        <tab-control :titles="['衣服', '鞋子', '裤子']" @tabItemClick="tabItemClick" />
        <!-- 2.展示内容 -->
        <h1>{{ pageContents[currentIndex] }}</h1>
        <!--  -->
        <tab-control :titles="['衣服', '鞋子', '裤子']" @tabItemClick="tabItemClick">
            <!-- 独占默认插槽的简写<template v-slot="props">
                 写法二          v-slot:default="props" -->
            <template #default="props">
                <button>{{ props.item }}</button>
            </template>

        </tab-control>

        <tab-control :titles="['衣服', '鞋子', '裤子']" @tabItemClick="tabItemClick">
            
            <template #default="props">
                <a href="#">{{ props.item }}</a>
            </template>
        </tab-control>

    </div>
</template>

<script>
import TabControl from './TabControl.vue'
export default {
    components: {
        TabControl
    },
    data() {
        return {
            pageContents: ["衣服列表", "鞋子列表", "裤子列表"],
            currentIndex: -1
        }
    },
    methods: {
        tabItemClick(index) {
            console.log("app:", index);
            this.currentIndex = index
        }
    }
}
</script>

<style scoped></style>