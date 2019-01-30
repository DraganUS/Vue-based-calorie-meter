<template>
  <div class="helloWorld">
    <div id="counterContainer">
      <div id="top">
        <i class="fas fa-heartbeat"></i>
        <h3>Vue.je Calorie Couner</h3>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

div#counterContainer  {
  border-radius: 1em;
  background: #fff;
  width: 746px;
  min-height: 471px;
  overflow: hidden;
}
div#top{
  position: relative;
  background: #019688;
  width: 100%;
  height: 100px;
  text-align: center;
  overflow: hidden;
}
div#top i{
  position: absolute;
  top: -8px;
  left: 2px;
  font-size: 131px;
}
div#top h3{
  color: #fff;
  font-weight: 400;
  font-size: 42px;
  margin: 0;
  margin-top: 21px;
}

</style>
