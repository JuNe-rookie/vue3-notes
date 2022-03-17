<template>
  <h1>App组件</h1>
  <p>姓名：{{name}}</p>
  <p>年龄：{{age}}</p>
  <p>工作种类：{{job.type}}</p>
  <p>工作薪水：{{job.salary}}</p>
  <button @click="changeInfo">修改信息</button>
</template>

<script>
import {ref} from 'vue';
export default {
  name: 'App',
  setup() {
    let name = ref("Tom");
    let age = ref(23);
    let job = ref({
      type: "测试工程师",
      salary: "0k",
    });

  function changeInfo() {
    name.value = "李四";
    age.value = 48;
  }

    return {
      name,
      age,
      job,
      changeInfo,
    };
  }
}
</script>

<style>

</style>
