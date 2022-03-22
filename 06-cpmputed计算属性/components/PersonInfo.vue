<template>
  <h1>个人信息</h1>
  姓：<input type="text" v-model="person.firstName">
  名：<input type="text" v-model="person.lastName">
  <br>
  <p>姓名：{{person.fullName}}</p>
  <br>
  全名:<input type="text" v-model="person.fullName">
</template>

<script setup>
  import {reactive,computed} from "vue";
  const person = reactive({
    firstName:"",
    lastName:"",
  });

  // 计算属性简写：没有考虑计算属性被修改
  person.fullName = computed(() => {
    return person.firstName +" " + person.lastName
  });

  // 计算属性完整写法，考虑计算属性被修改。是一个对象
  person.fullName = computed({
    get(){
      return person.firstName + " " + person.lastName;
    },
    set(value){
      const nameArr = value.split(" ")
      person.firstName = nameArr[0]
      person.lastName = nameArr[2]
    }
  })
</script>

<style lang="css">
input{
  display: block;
}
*{
  padding-left: 10px;
}
</style>
