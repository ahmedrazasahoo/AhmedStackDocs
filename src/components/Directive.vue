<script>
import { handleError } from 'vue';


export default{
    data(){
        return{
            name : "Ahmed",
            isActive : true,
            classObject: {
                "bg-wrapper": true,
                'text-danger': true
            }

        }
    },

  methods:{
    handleError(){
        // this.isActive=false
        this.classObject['bg-wrapper'] = true
        console.log("Show in the console")

    },
    reset(){
        this.classObject['bg-wrapper'] = false
        // this.isActive=true
        console.log("Show in the console and Reset This One")
    },
  

  }
}
</script>
<template>
  <h2>Class Directive</h2>
  <h4>Dear Sir {{ name }}</h4>
  <h3
    :class="{ 'text-danger': isActive }"
  >
  This one Just the PRACTICE class added based one the active
  </h3>
   <h3
    :class="classObject"
  >
  This one Just the PRACTICE classObject
  </h3>
  
  
 <div class="wrapper">
     <button @click="handleError"> Error Show</button>
   <button @click="reset"> ReSet</button>
 </div>
</template>
<style scoped>
.bg-wrapper{
    background-color: cadetblue;
    text-align: center;
    font-size: x-large;
    padding: 10px;
}

/* .text-danger{
  color: rgb(0, 0, 0);
} */

.wrapper{
    display: block;
    justify-content: space-between; 
}
.text-danger{
 text-align: center;
 color: brown;
 font-size: xx-large;
 text-shadow: 2rem;
}
h2 {
  text-align: center;
  color: rgb(35, 54, 14);
  font-size: xx-large;
}
button{
    text-align: center;
    font-size: medium;
    padding: 20px;
    background: #3d792e;
    color: azure;
    height: 30px;
    width: 200px;
    border-radius: 30px;
}
</style>
