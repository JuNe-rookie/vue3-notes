<template>
  <h1>App组件</h1>
  <p>姓名：{{person.name}}</p>
  <p>职业：{{person.job}}</p>
  <button @click="test">测试触发组件的Hello事件</button>
  <a href=""></a>
</template>

<script>
import {reactive} from 'vue';
export default {
  name: 'PersonInfo',

  // Vue3需要在外面声明props，emits、attrs和slots
  props:['age'],
  emits:['hello'],

  setup(props, context) {
    console.log(props);
    console.log(context);
    let person = reactive({
      name: "张三",
      job: "法外狂徒"
    });

    function test() {
      context.emit('hello', 6666)
    }

    return {
      person,
      test
    };
  }
}
</script>

<style>
p{
  font-weight: bolder;
  font-size: x-large;
}

</style>
