<template>
  
    <div id="counterContainer">
      <div id="top">
        <i class="fas fa-heartbeat"></i>
        <h3>Vue.je Calorie Couner</h3>
      </div>
      <ul id="description">
        <li>DESCRIPTION</li>
        <li>CALORIES</li>
        <li>FAT</li>
        <li>CARBS</li>
        <li>PROTEIN</li>
      </ul>
      <hr> 
        <ul v-for="(value, index) in item">
        <li>{{ value.descrtiopion }}</li>
        <li>{{ value.calories }}</li>
        <li>{{ value.fat }}</li>
        <li>{{ value.carbs }}</li>
        <li>{{ value.protein }}</li>
      </ul>
      <div id="total">
        <span>Total</span>
        <span>1231</span>
        <span>21</span>
        <span>213</span>
        <span>21323</span>
      </div>
      <i class="fas fa-plus-circle"></i>
    </div>
  
</template>

<script>
export default {
  name: 'calorieCalculator',
  data(){
    return {
      newDescription: "",
      newCalories: "",
      newFat: "",
      newCarbs: "",
      newProtein: "",
      item: [
        { 
          descrtiopion: "This is an item1",
          calories: 225,
          fat: 12,
          carbs: 23,
          protein: 29
        },
        { 
          descrtiopion: "This is an item2",
          calories: 225,
          fat: 12,
          carbs: 23,
          protein: 29
        },
        { 
          descrtiopion: "This is an item3",
          calories: 225,
          fat: 12,
          carbs: 23,
          protein: 29
        }
      ]
    }
  },
  methods: {

  }

}
</script>

<style scoped>

div#counterContainer  {
  border-radius: 1em;
  background: #fff;
  width: 746px;
  position: relative;
  padding-bottom: 60px;
}
div#top{
  border-radius: 1em 1em 0 0 ;
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
ul li:nth-of-type(1){
  width: 30%;
}
ul li{
  width: 100px;
}
ul#description li{
  font-weight: 900;
  border: none;
}
ul {
  margin: 0;
  padding: 17px;
  list-style-type: none;
  display: flex;
  justify-content: space-around;
}
ul li{
  border-bottom: 1px solid #354250;
}
hr{
  margin: 0;
}
div#total{
  background: #e7e7e7;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}
div#total span:nth-of-type(1){
  text-align: end;
}
div#total span{
  font-weight: 800;
  width: 100px;
  margin: 12px;  
}
i.fa-plus-circle{
  position: absolute;
  bottom: -10px;
  right: -10px;
  font-size: 77px;
  color: #019688;
}
</style>
