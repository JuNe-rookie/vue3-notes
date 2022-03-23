<template>
  <h1>{{x.y}}</h1>
  <button @click="x.y++">点击x.y +1</button>
  <hr>
  <h1>名字：{{person.name}}</h1>
  <h1>年龄：{{person.age}}</h1>
  <h1>薪资：{{person.job.work.salary}}</h1>
  <button @click="person.name+='e'">点击修改name</button>
  <button @click="person.age++">点击修改年龄</button>
  <button @click="person.job.work.salary++">点击涨薪</button>
</template>

<script setup>
import {shallowReactive, shallowRef} from "vue"

let x = shallowRef({
  y:0
})

// let person = shallowReactive({  // 只会把最外面一层作为响应式
let person = shallowReactive({
  name: "张三",
  age: 22,
  job:{
    work:{
      salary: 3
    }
  }
})

</script>


<style lang="css">

</style>
