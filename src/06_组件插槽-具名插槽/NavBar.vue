<template>
    <div class="nav-bar">
        <div class="left">
            <slot name="left">left</slot>
        </div>
        <div class="center">
            <slot name="center">center</slot>
        </div>
        <div class="right">
            <slot name="right">right</slot>
        </div>

        <!-- 具名插槽有一个特殊的attribute--name
             一个不带name的slot，会带一个隐含的名字：default -->
        <div class="other">
            <slot name="default"></slot>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.nav-bar {
    display: flex;
    height: 44px;
    line-height: 44px;
    text-align: center;
}

.left {
    width: 80px;
    background-color: orange
}

.center {
    flex: 1;
    background-color: skyblue;
}

.right {
    width: 80px;
    background-color: aqua;
}
</style>