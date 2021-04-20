
<template>
   <div class="section-container">
        <form onsubmit="return false" class="form-box text-left">
            <div class = "form-element-container" v-for="item in formInputElements" :key="item.formValueKey">
                <div class="form-element font-icon">
                   <div class = "form-label">{{item.labelName}}</div>
                      <input class = "form-input" type = "text" id="name"
                      :value="formData[item.formValueKey]"
                      @input="changeFormData({[item.formValueKey]:$event.target.value})" />
                      <i :class="item.iconClass"></i>
                </div>
            </div>
           <div>Upload Profile Picture</div>
           <div v-on:click="onFileChange">
             <div v-for = "picture in items"  :key="picture.image">
                 <div v-if="!picture.image">
                      <input type="file" @change="onFileChange(picture, $event)">
                </div>
                     <div v-else>
                         <img :src="picture.image" class="circleBase circle1" width="120px" /><br>
                         <button @click="removeImage(picture)">Remove image</button>
                    </div>
            </div>
            </div>
        </form>
    </div>
</template>
  
<script>

export default {
    name:"UserInputElements",
    data(){
        return{
            formInputElements:[
                {labelName:'First Name', formValueKey:'firstName',placeholder:'Enter First Name'},
               {labelName:'Last Name', formValueKey:'lastName',placeholder:'Enter Last Name'} ,
                 {labelName:'Department', formValueKey:'department',placeholder:'Enter Department'},
               {labelName:'Academic Year', formValueKey:'academicYear',placeholder:'Enter Academic Year'},
              
     ],
     file:null,
     items: [
       {
         image: false,
       }
    ],
          }
    },
    props:{
        formData:Object,
        },
    methods:{
       changeFormData(value){
            console.log("Child element value : ",value);
            this.$emit("changeFormData",value);
        },
        onFileChange(picture, e) {
            var files = e.target.files || e.dataTransfer.files;
            if (!files.length)
            return;
            this.createImage(picture, files[0]);
       },
        createImage(picture, file) {
            var image = new Image();
            var reader = new FileReader();
            console.log(image);
            reader.onload = (e) => {
            picture.image = e.target.result;
        };
            reader.readAsDataURL(file);
             this.$emit('onFileChange', picture)
        },
          removeImage: function (picture) {
              picture.image = false; 
        }
  }

}
</script>


 