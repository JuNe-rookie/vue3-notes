<template>
  <PersonInfo @hello="showHelloMsg" age=20 />
</template>

<script>
import PersonInfo from "./components/PersonInfo.vue"
export default {
  components: {
    PersonInfo
  },
  setup(){
    function showHelloMsg(value) {
      alert(`Hello,接受到的数据为:${value}`)
    }


    return{
      showHelloMsg
    }
  }
}
</script>

<style>

</style>