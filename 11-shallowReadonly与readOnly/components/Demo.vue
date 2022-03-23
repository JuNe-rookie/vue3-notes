<template>
  <h1>和为：{{sum}}</h1>
  <button @click="sum++">点击++</button>
  <hr>
  <h1>名字：{{person.name}}</h1>
  <h1>年龄：{{person.age}}</h1>
  <h1>薪资：{{person.job.work.salary}}</h1>
  <button @click="person.name+='e'">点击修改name</button>
  <button @click="person.age++">点击修改年龄</button>
  <button @click="person.job.work.salary++">点击涨薪</button>
</template>

<script setup>
import {reactive, ref, shallowReadonly} from "vue"

let person = reactive({
  name: "张三",
  age: 22,
  job:{
    work:{
      salary: 3
    }
  }
})
person = shallowReadonly(person)

let sum = ref(0)

</script>


<style lang="css">

</style>
