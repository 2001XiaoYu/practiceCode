<template>
    <div class="app">
        <!-- 1.内容是button -->
        <show-message title="哈哈哈">
            <button>我是按钮元素</button>
        </show-message>

        <!-- 2.内容是超链接 -->
        <show-message>
            <a href="https://www.baidu.com">百度一下</a>
        </show-message>

        <!-- 3.内容是一张图片 -->
        <show-message>
            <img src="@/img/fighting.png" alt="">
        </show-message>

        <!-- 4.默认没有传任何东西 -->
        <show-message></show-message>
    </div>
</template>

<script>
import ShowMessage from './ShowMessage'

export default {
    components: {
        ShowMessage
    }
}
</script>

<style scoped></style>