<template>
    <div class="infos">
        <h2>姓名：{{ name }}</h2>
        <h2>年龄：{{ age }}</h2>
        <h2>身高：{{ height }}</h2>

        <h2>Message: {{ showMessage }}</h2>
        <hr>
     </div>
</template>

<script>
    export default {
        // 作用：接收父组件传递过来的属性
        //1.props数组语法
        //弊端: 1>不能对类型进行验证 2>没有默认值
        // props: ["name", "age", "height"]

        //2.props对象语法（必须掌握）
        props: {
            name: {
                type: String,
                default: "我是默认name"
            },
            age: {
                type: Number,
                required: true,
                default: 0
            },
            height: {
                type: Number,
                default: 2
            },
            friend: {
                type: Object,
                default() {
                    return { name: "James"}
                }
            },
            hobbies: {
                type: Array,
                default() {
                    return ["唱", "跳", "rap", "篮球"]
                }
            },
            showMessage: {
                type: String,
                default: "我是showMessage"
            }
        }
    }
</script>

<style scoped>

</style>