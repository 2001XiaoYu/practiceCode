<template>
    <div class="app">
        <nav-bar>
            <!-- v-slot:语法糖 # -->
            <template v-slot:left>
                <button>{{ leftText }}</button>
            </template>

            <template #center>
                <span>内容</span>
            </template>

            <template #right>
                <a href="#">登录</a>
            </template>
        </nav-bar>

        <!-- nav-bar只给一个插槽传入数据 -->
        <nav-bar>
            <template v-slot:[position]>
                <a href="#">注册</a>
            </template>
        </nav-bar>
        <button @click=" position = 'left' ">左边</button>
        <button @click=" position = 'center' ">中间</button>
        <button @click=" position = 'right' ">右边</button>
    </div>
</template>

<script>
import NavBar from './NavBar'
export default {
    components: {
        NavBar
    },
    data() {
        return {
            position: "center",
            leftText: "返回"
        }
        
    }
}
</script>

<style scoped></style>