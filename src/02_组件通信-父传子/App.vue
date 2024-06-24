<template>
    <!-- 1.展示patrickstar的个人信息 -->
     <!-- 如果当前的属性是一个非prop的attribute，
        那么该属性会默认添加到子组件的根元素上 -->
    <show-info name="patrickstar" :age="23" :height="1.78" 
               address="郑州市" abc="cba" class="active" />

    <!-- 2.展示Bob的信息 -->
    <show-info name="Bob" :age="30" :height="1.68" />

    <!-- 3.展示默认值 -->
    <show-info :age="6" show-message="哈哈哈" />
</template>

<script>
import ShowInfo from './ShowInfo'
    export default {
        components: {
            ShowInfo
        }
    }
</script>

<style scoped>

</style>