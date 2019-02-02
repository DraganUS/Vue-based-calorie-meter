<template>
  <div id="app">
    <calorieCalculator/>
  </div>
</template>

<script>
import calorieCalculator from './components/calorieCalculator.vue'

export default {
  name: 'app',
  components: {
    calorieCalculator
  }
}
</script>

<style>
#app {
  min-height: 800px;
  width: 100%;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #2c3e50;
}
</style>
