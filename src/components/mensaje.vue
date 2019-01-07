<template>
 <div class="mensaje">
   <div class="contenedor">
     <div class="logo"><img :src="require('../assets/cactus2.png')" alt="" /></div>
     <div class="user"><p> ¡Enhorabuena, {{$route.params.user}} <br>Tu perfil ha sido actualizado!</p></div>   
   </div>
 </div>
</template>

<script>
    
 export default{
   name:'mensaje'   
 }
</script>


<style scoped>
  .mensaje {    
    margin: auto;
    max-width: 1000px;
  }  
  .contenedor{
    margin: auto;
    
    max-height: 300px;
    margin-top: 20%;
    font-family: calibri, sans-serif;
    color: gray;
      }
  .logo{
    width: 40%;
    float: left;
      
  }.logo img{
    max-width:100%;
    max-height:100%;
  }
  .user{
    width: 60%;
    float: left;
  }
  p{
    font-weight: normal;
    line-height: 1.6;
    font-family: "roboto_slabthin";
    font-size: 40px;
    color: #454545;
    text-align: left;
    margin-top: 0px;
  }
  
</style> 