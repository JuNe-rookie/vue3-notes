<template>
  <h1>名字：{{person.name}}</h1>
  <h1>年龄：{{person.age}}</h1>
  <h1>薪资：{{person.job.work.salary}}</h1>
  <h2 v-show="person.car">座驾：{{person.car}}</h2>
  <button @click="person.name+='e'">点击修改name</button>
  <button @click="person.age++">点击修改年龄</button>
  <button @click="person.job.work.salary++">点击涨薪</button>
  <button @click="showRawPerson">输出原始的信息</button>
  <button @click="getCar">买一辆车</button>
  <button @click="changeCarName">换车</button>
</template>


<script setup>
import {reactive, toRaw, markRaw} from "vue"

let person = reactive({
  name: "张三",
  age: 22,
  job:{
    work:{
      salary: 3
    }
  }
})

function showRawPerson() {
  const p = toRaw(person)
  console.log(p)
}

function getCar() {
  let car = {name: "自行车", price: 200}
  person.car = markRaw(car)
}

function changeCarName() {
  let newName = person.car.name += "!"
  console.log(newName)
  return newName
}

</script>


<style lang="css">

</style>
