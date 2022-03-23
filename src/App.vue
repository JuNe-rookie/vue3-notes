<template>
  <Demo />
</template>

<script setup>

import {defineAsyncComponent} from "vue"
const Demo = defineAsyncComponent(()=>import('./components/Demo.vue'))


</script>

<style>

</style>