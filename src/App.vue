<template>

     <div id="app">
         <div class = "container d-flex container-box">
          <UserInputElements :formData="formData" @changeFormData="changeFormData($event)"/>
          <GeneratedCardComponent :formData = "formData"/>
        </div>
     
     <div class="circleBase circle2"  style="cursor: pointer;" width="120px">
        <!-- <UserInputElements :image-url ="require('./assets/image2.png')" /> -->
     </div>
     </div>
    
</template>

<script>

import UserInputElements from'./components/UserInputElements';
import GeneratedCardComponent from './components/GeneratedCardComponent';
export default {
  name: 'App',
  components: {
    UserInputElements,
    GeneratedCardComponent
   },
  data(){
    return{
     
       formData:{
         firstName:"",
         lastName:"",
         department:"",
         academicYear:""
       },
       items: [
       {
         image: false,
       }
    ],
    };
      },
  methods:{
    changeFormData(keyObject){
      console.log("Parent Element Value: ",keyObject);
      this.formData = Object.assign({},this.formData,keyObject)
    },
   }
}

</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color:green;
 } 
.form-element {
  margin: 5px;
  min-width: 200px;
}
.form-box {
  width: 100%;
  max-width: 285px;
}
.form-label {
width: 152px;
height: 24px;
left: 55px;
top: 60px;

font-family: Inter;
font-style: normal;
font-weight: normal;
font-size: 20px;
line-height: 24px;

color: #000000;
}
.form-input {
width: 257px;
height: 43px;
left: 55px;
top: 98px;

background: #FFFFFF;
border: 1px solid #C5C0C0;
box-sizing: border-box;
border-radius: 6px;
}
.academic-year{
 position:relative;
width: 233px;
height: 90px;
left: 20px;
top: 210px;
text-align: center;
font-family: Inter;
font-style: normal;
font-weight: 600;
font-size: 20px;
line-height: 24px;

color: #000000;
}
.department-name{
  position:relative;
 width: 233px;
height: 90px;
left: 20px;
top: 120px;
text-align: center;
font-family: Inter;
font-style: normal;
font-weight: 600;
font-size: 20px;
line-height: 24px;

color: #000000;
}

.section-container {
width: 550px;
height: 585px;
background: white;
border: 1px solid #AAA2A2;
box-sizing: border-box;
 }
 .card-container {
  position: relative;
  width: 300px;
  height: 380px;
  top:100px;         
  left: 110px;
vertical-align: 100%;
background:white;
border: 1px solid black;
border-radius: 10px;

}

.card-name{
 position:relative;
 width: 233px;
height: 90px;
left: 20px;
top: 70px;
text-align: center;
font-family: Inter;
font-style: normal;
font-weight: 600;
font-size: 20px;
line-height: 24px;

color: #000000;
}
.circleBase {
  border-radius: 50%;
  position: absolute;
}

.circle1 {
  position: absolute;
  width: 200px;
  height: 200px;
  background: white;
  border: 1px solid #000;
}
.circle2 {
  position: absolute;
  width: 200px;
  height: 200px;
  left:835px;
  top:0px;
  background: white;
  border: 1px solid #000;
}
.img {
  width: 30%;
  margin: auto;
  display: block;
  margin-bottom: 10px;
}
button{
  position:relative;
 top:180px;
 width:200px;
}
</style>
