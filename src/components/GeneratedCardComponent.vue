<template>
<keep-alive>
<div>
        <div class="section-container">
            <div class="card-container">
                
           
            <div class="academic-year">
              {{formData.academicYear}}
            </div>
            <div class="card-name">
             {{formData.firstName}} {{formData.lastName}}
            </div>
            <div class="department-name">
             Dept of {{formData.department}}
            </div>
           
          </div>
           
           <!-- <img alt="Vue logo" src="./assets/image.jpg"> -->
    <!-- <component v-bind:is="component" /> -->
    <!-- <UserInputElements v-bind:img = "img" width="200" /> -->
     <!-- <div>
      <div>
        <input v-model="img"/>
      </div>
      <UserInputElements v-bind:img="img"></UserInputElements>
    </div> -->
      <!-- <div class = "form-label">Upload Profile Picture</div><br> -->
                 <!-- <img v-bind:src="require('../assets/' + img)" width="200" /> -->
  <!-- `<div class="user-card"> -->
     <!-- <UserInputElements :image-url="require('~/assets/image.jpg')" /> -->
    <!-- <UserInputElements {{item.name}}/> -->
    <!-- <section>{{item.name}}</section> -->
             <!-- </div> -->
        <!--    </div> -->
      </div>
      
      </div>
      </keep-alive>
</template>
<script>
// import UserInputElements from'./components/UserInputElements';
export default {
       name:"GeneratedIDCard",
       components:{
        //  UserInputElements
       },
       data(){
        return{
      //  img: "image.jpg"
          }
    },
  
       props:{
          // img:Object,
           formData:Object,
           
       }
};
</script>