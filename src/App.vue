<template>
  <h1>Little Indian Resto</h1>
  <ul>
    <dish-details
      v-for="dish in dishes"
      :key="dish.id"
      :name="dish.name"
      :description="dish.description"
      :price="dish.price"
      :isFavourite="dish.isFavourite"
      :id="dish.id"
      @toggleFavouriteStatus="toggleFavouriteStatus"
    />
  </ul>
</template>

<script>
import DishDetails from "./components/DishDetails.vue";

export default {
  name: "App",
  components: {
    DishDetails,
  },
  data(){
    return{
      dishes:[
        {
          id:"avi",
          name:"buuterchicken",
          description:"finger licking good",
          price:"350",
          isFavourite:true

        },
        {
          id:"vaibhav",
          name:"chole",
          description:"chole seeds with curry",
          price:"150",
          isFavourite:true

        },
        {
          id:"akshatha",
          name:"Fish fry",
          description:"deep fried sea fish from deep ocean",
          price:"100",
          isFavourite:true

        }
      ]
    }
  },
  methods:{
    //to get seleccted dishDetail from childcomponent
    toggleFavouriteStatus(dishID){
      // console.log("dishid in parent",dishID);
      let identifiedDish=this.dishes.find((dish)=>dish.id===dishID)
      // console.log("identifiedDish",identifiedDish);
      identifiedDish.isFavourite=!identifiedDish.isFavourite
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  border: 5px solid blue;
  border-radius: 10px;
}
h1{
  background-color: aqua;
  margin-top: 0;
}
h2{
  background-color: crimson;
}


</style>
