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
        <ul v-for="(value, index) in item" >
        <li>{{ value.descrtiopion }}</li>
        <li>{{ value.calories }}</li>
        <li>{{ value.fat }}</li>
        <li>{{ value.carbs }}</li>
        <li>{{ value.protein }}</li>
        <i class="fas fa-times" @click="deleteFromList(index)"></i>
      </ul>
      <div id="total">
        <span>Total</span>
        <span>{{ totalCalories }}</span>
        <span>{{ totalFat }}</span>
        <span>{{ totalCarbs }}</span>
        <span>{{ totalProtein }}</span>
      </div>
      <ul>
        <li><input  placeholder="enter description *" type="text"  v-model="newDescription"></li>
        <li><input  placeholder="enter calories *" type="number"  v-model="newCalories"></li>
        <li><input  placeholder="enter fat" type="number"  v-model="newFat"></li>
        <li><input  placeholder="enter carbs" type="number"  v-model="newCarbs"></li>
        <li><input  placeholder="enter protein" type="number"  v-model="newProtein"></li>    
      </ul>
      <i @click="addItem(),calculateTotal()"  class="fas fa-plus-circle"></i>
    </div>
  
</template>

<script>
export default {
  name: 'calorieCalculator',
  data(){
    return {
      newDescription: "",
      newCalories: 0,
      newFat: 0,
      newCarbs: 0,
      newProtein: 0,
      totalCalories: 0,
      totalFat: 0,
      totalCarbs: 0,
      totalProtein: 0,
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
          calories: 222,
          fat: 12,
          carbs: 23,
          protein: 29
        },
        { 
          descrtiopion: "This is an item3",
          calories: 111,
          fat: 12,
          carbs: 23,
          protein: 29
        }
      ]
    }
  },
  methods: {
    addItem(){

      if (this.newDescription !== '' && this.newCalories !== '') {
         this.item.push({
        descrtiopion: this.newDescription,
        calories: parseInt(this.newCalories),
        fat: parseInt(this.newFat),
        carbs: parseInt(this.newCarbs),
        protein: parseInt(this.newProtein)
      });
        this.newDescription = "";
        this.newCalories = 0;
        this.newFat = 0 ;
        this.newCarbs = 0;
        this.newProtein = 0;
      } else{
        alert("You need to enter descrtiopion and calories")
      }

    },
    calculateTotal(){
      this.totalCalories=0;
      this.totalFat = 0 ;
      this.totalCarbs = 0;
      this.totalProtein = 0;
      for (let i = 0; i < this.item.length; i++) {
      this.totalCalories += this.item[i].calories;
      this.totalFat += this.item[i].fat;
      this.totalCarbs += this.item[i].carbs;
      this.totalProtein += this.item[i].protein;
      }
      return this.totalCalories,this.totalFat, this.totalCarbs, this.totalProtein;
    },
    deleteFromList(index){
        this.item.splice(0, 1);    
       }, 
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
  top: -17px;
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
ul li input{
  border: none;
  width: 100%;
  height: 25px;
}
i{
  cursor: pointer;
}
i.fa-times{
  font-size: 28px;
  color:#e7e7e7;
}
i.fa-times:hover{
color: #444444;
}
i.fa-plus-circle{
  position: absolute;
  bottom: -10px;
  right: -10px;
  font-size: 77px;
  color: #019688;
}
</style>
