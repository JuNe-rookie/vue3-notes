<template>
  <h1>App组件</h1>
  <p>姓名：{{name}}</p>
  <p>年龄：{{age}}</p>
  <button @click="sayHello">按钮</button>
</template>

<script>
export default {
  name: 'App',
  setup() {
    let name = "Tom";
    let age = 23;

    const sayHello = function() {
      alert(`我叫${name},今年${age}岁。`);
    };


    return {
      name,
      age,
      sayHello
    };
  }
}
</script>

<style>

</style>
