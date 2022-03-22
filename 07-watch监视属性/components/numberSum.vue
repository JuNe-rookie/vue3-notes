<template>
  <h1>当前求和为：{{ sum }}</h1>
  <button @click="sum++">点击+1</button>
  <hr>
  <h1>{{msg}}</h1>
  <button @click="msg+='o'">点击</button>
  <hr>
  <h1>名字：{{person.name}}</h1>
  <h1>年龄：{{person.age}}</h1>
  <h1>薪资：{{person.job.work.salary}}</h1>
  <button @click="person.name+='e'">点击修改name</button>
  <button @click="person.age++">点击修改年龄</button>
  <button @click="person.job.work.salary++">点击涨薪</button>
</template>

<script>
import { ref, reactive, watch } from "vue";
export default {
  setup() {
    let sum = ref(0)
    let msg = ref("hello")
    let person = reactive({
      name: "张三",
      age: 23,
      job:{
        work:{
          salary: 2
        }
      }
    })

    // 情况1：监视ref定义的单个响应式数据
    // watch(sum, (newValue, oldValue)=>{
    //   console.log("sum值变化", newValue, oldValue);
    // })
    // 情况2：监视ref定义的多个响应式数据
    // watch([sum, msg], (newValue, oldValue)=>{
    //   console.log("sum或者msg值变化", newValue, oldValue);
    // },{immediate:true})

    // 情况3：监视reactive监视的对象响应式数据   此处无法正确获取oldValue
    // watch(person,(newValue, oldValue)=>{
    //   console.log("变化了", newValue, oldValue);
    // },{deep: false})

    // 情况4：监视reactive所定义的一个响应式数据中的某个属性
    // watch(()=>person.age,(oldValue, newValue)=>{
    //   console.log("改变了", oldValue, newValue);
    // })
    // 情况5：监视reactive所定义的一个响应式数据中的某些属性
    // watch([()=>person.age, ()=>person.name], (oldValue, newValue)=>{
    //   console.log("age或者name改变了", oldValue, newValue);
    // })

    // 特殊情况
    watch(()=>person.job,(oldValue, newValue)=>{
      console.log("person的job改变了", oldValue, newValue);
    }, {deep: true})
    
    return {
      sum,
      msg,
      person,
    }
  }
}
</script>


<style lang="css">

</style>
