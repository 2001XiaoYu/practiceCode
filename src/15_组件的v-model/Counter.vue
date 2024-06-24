<template>
    <div class="counter">Counter: {{ modelValue }}</div>
    <button @click="changeCounter">修改counter</button>
</template>

<script>
    export default {
        props: {
            modelValue: {
                type: Number,
                default: 0
            }
        },
        emits: ["update:modelValue"],
        methods: {
            changeCounter() {
                this.$emit("update:modelValue", 200)
            }
        }
    }
</script>

<style scoped>
.counter {
    font-size: 500px;
}
</style>