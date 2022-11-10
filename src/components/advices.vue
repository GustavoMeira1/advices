<template>
  <v-container class="mainContainer">
    <v-card class="mainCard">
      <div class="text">
        <p class="advId">ADVICE #{{advId}}</p>
        <p class="advice">"{{advice}}"</p>
      </div>
      <div class="ligns">
        <div class="divider"></div>
        <div class="ball"></div>
        <div class="ball"></div>
        <div class="divider"></div>
      </div>
      <v-btn @click="getAdvice()" class="btn"><v-icon class="teste">mdi-dice-5</v-icon></v-btn>
    </v-card>
  </v-container>
</template>

<script>
import axios from 'axios';
  export default {
    name: 'main-advices',

    data(){
      return{
        advId:"",
        advice: "",
        
      }
    },

  mounted () {
    this.getAdvice();
  },

  methods:{
    getAdvice(){
      axios
  .get('https://api.adviceslip.com/advice')
  .then(response => (this.advId = response.data.slip.id, this.advice = response.data.slip.advice))
  console.log(this.info)
    }
  }
  }
</script>

<style>
@media only screen and (max-width:450px){
.mainContainer{
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
}
.text{
  height: 150px;
}
.mainCard{
  background-color: hsl(217, 19%, 24%) !important;
  height: 320px;
  width: 550px;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  flex-direction: column;
}
.advId{
  color: hsl(150, 100%, 66%);
  letter-spacing: 3px;
  font-size: 12px;
}
.advice{
  color: white;
  font-size: 25px;
  text-align: center;
  padding: 20px;
}
.ligns{
  display: flex;
  transform: translateY(70px);
}
.divider{
  background-color: hsl(217, 19%, 38%);
  height: 1px;
  width: 140px;
  margin: 5px;
}
.ball{
  background-color: white;
  height: 15px;
  width: 6px;
  margin: 5px;
  border-radius: 5px;
  transform: translateY(-8px);
}
.btn{
  margin-top: 10px;
  background-color: hsl(150, 100%, 66%) !important;
  border-radius: 100% !important;
  height: 65px !important;
  transform: translateY(70px);
}
.btn:hover{
  box-shadow: 0 0 35px hsl(150, 100%, 66%),0 0 15px hsl(150, 100%, 66%) inset;
}

}
@media only screen and (min-width:450px){
.mainContainer{
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
}
.text{
  height: 150px;
}
.mainCard{
  background-color: hsl(217, 19%, 24%) !important;
  height: 320px;
  width: 550px;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  flex-direction: column;
}
.advId{
  color: hsl(150, 100%, 66%);
  letter-spacing: 2px;
}
.advice{
  color: white;
  font-size: 25px;
  text-align: center;
  padding: 20px;
}
.ligns{
  display: flex;
  transform: translateY(70px);
}
.divider{
  background-color: hsl(217, 19%, 38%);
  height: 1px;
  width: 200px;
  margin: 5px;
}
.ball{
  background-color: white;
  height: 15px;
  width: 6px;
  margin: 5px;
  border-radius: 5px;
  transform: translateY(-8px);
}
.btn{
  margin-top: 10px;
  background-color: hsl(150, 100%, 66%) !important;
  border-radius: 100% !important;
  height: 65px !important;
  transform: translateY(70px);
}
.btn:hover{
  box-shadow: 0 0 35px hsl(150, 100%, 66%),0 0 15px hsl(150, 100%, 66%) inset;
}

}
</style>
