<template>
  <h1>名字：{{name}}</h1>
  <h1>年龄：{{person.age}}</h1>
  <h1>薪资：{{salary}}</h1>
  <button @click="name+='e'">点击修改name</button>
  <button @click="person.age++">点击修改年龄</button>
  <button @click="salary++">点击涨薪</button>
</template>

<script setup>
import {reactive, toRef, toRefs} from "vue"

let person = reactive({
  name: "张三",
  age: 22,
  job:{
    work:{
      salary: 3
    }
  }
})
let name = toRef(person, 'name')

let salary = toRefs(person)
console.log(salary);

</script>


<style lang="css">

</style>
