<template>
  <h1>当前求和为：{{ sum }}</h1>
  <button @click="sum++">点击+1</button>
</template>

<script>
import { ref, onBeforeMount } from "vue"
export default {
  setup() {
    let sum = ref(0)
    onBeforeMount(()=>{
      console.log("----------onBeforeMount----------");
    })

    return {
      sum
    }
  }
}

</script>


<style lang="css">

</style>
