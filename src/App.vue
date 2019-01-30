<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  background: linear-gradient(205deg, rgba(99, 212, 4, 0.92) 0%, rgba(232, 255, 0, 0.92) 77%);
  height: 1000px;
  width: 100%;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #2c3e50;
}
</style>
