<template>
  <button @click="isShowDemo = !isShowDemo">切换显示/隐藏</button>
  <numberSum v-if="isShowDemo"/>
</template>

<script setup>
import numberSum from "./components/numberSum.vue"
import { ref } from "vue"

let isShowDemo = ref(true)
</script>

<style>

</style>