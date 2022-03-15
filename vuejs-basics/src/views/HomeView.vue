<template>
  <div class="home">
    <p>Resultado de 2+2: {{2+2}}</p>
    <p>Datos puestos con una funcion: {{printData}}</p>
    <button @click="showDataFunction" v-text="textButton">Show Data</button>
    <p v-if="showData">Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem non tempore eligendi voluptatum, consequuntur nobis fuga, expedita blanditiis voluptatem perspiciatis sed modi odio eius, autem officiis totam deserunt soluta ullam?</p>
    <Cards/>
    <div class="coloredDiv">
      <p v-bind:class="pClass"></p>
      <button @click="changeColor">Change Color</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Cards from "../components/Cards.vue"
export default {
  name: 'HomeView',
  components: {
    Cards
  },
    data() {
    return {
      data: "Printed from a function",
      showData:false,
      textButton:"Show Data",
      classColor: ["blue", "red", "green", "black", "orange", "yellow", "grey"],
      pClass: "blue",
    }

  },
  computed: {
    printData() {
      return this.data;
    }
  },
  methods:{
    showDataFunction(){
      this.showData = !this.showData;
      if(this.textButton === "Show Data"){
        this.textButton = "Hide Data"
      }else if(this.textButton === "Hide Data"){
         this.textButton = "Show Data"
      }  
    },
    changeColor(){
      let choosenClass = this.classColor[Math.floor(Math.random()*this.classColor.length)];
      this.pClass = choosenClass;
    }
  }
}
</script>

<style>

  .coloredDiv{
      display: flex;
    }

  .coloredDiv button{
    height: 25px;
  }
 
 .blue{
    width:100px;
    height: 100px;
    background-color: blue;
  }

  .red{
    width:100px;
    height: 100px;
    background-color: red;
  }

  .green{
    width:100px;
    height: 100px;
    background-color: green;
  }

  .yellow{
    width:100px;
    height: 100px;
    background-color: yellow;
  }

  .orange{
    width:100px;
    height: 100px;
    background-color: orange;
  }

  .black{
    width:100px;
    height: 100px;
    background-color: black;
  }

  .grey{
    width:100px;
    height: 100px;
    background-color: grey;
  }


</style>
