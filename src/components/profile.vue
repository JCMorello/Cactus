<template>
 <div class="profile">
   <div class="ficha">
     <h4>Ficha de usuario</h4>
     <div class="contenedor">
       <span>Nombre:</span>
       <input class="form-control w3-input border-bottom" v-model="nombre" placeholder="" disabled>
       <span>Apellidos:</span>
       <input class="form-control w3-input border-bottom" v-model="apellidos" placeholder="" disabled>
       <span>Descripcción:</span>
       <textarea rows="8" cols="92" disabled >{{descripcion}}</textarea>
       <button v-show="mostrar" v-on:click="borrar()" class="btnBorrar btn btn-primary w3-button w3-round-small" >Borrar Todo</button>
     </div>
   </div>
   <div class="social">
     <h4>Social</h4>
     <div class="contenedor">
       <ul>
         <li v-for="social in socials">
           <a :href="social.link" target="_blank">
             <img :src="social.url" alt="" />
             <p>{{social.name}}</p>
           </a>
         </li>
       </ul>
              
     </div>
   </div>
     
   <div class="formulario">
     <div class="ficha">

       <div class="formNombre">
         <p>Nombre</p>
         <input class="form-control w3-input w3-border w3-round-large" v-model="nombre" placeholder="" v-on:keyup="comprobarTexto">
       </div>
       <div class="formApellidos">
         <p>Apellidos</p>
         <input class="form-control w3-input w3-border w3-round-large" v-model="apellidos" placeholder="" v-on:keyup="comprobarTexto">
       </div>
       <div class="formDescripcion" >
         <p>Descripción</p>
         <textarea rows="6" cols="30" class="form-control w3-input w3-border w3-round-large" v-model="descripcion" v-on:keyup="comprobarTexto">{{descripcion}}</textarea>
         
       </div>

     </div>
     <div class="boton">
       <router-link :to="{ name: 'mensaje', params: { user: nombre }}">
         <button class="btnGuardar btn btn-primary w3-button w3-round-large">Guardar</button>
       </router-link>

     </div>
    </div>
   
  </div> 
</template>
<script>
  
import mensaje from "@/components/mensaje.vue"
 export default{
  name:'profile',
  data (){
    return{
      title:'profile test',
      nombre:'',
      apellidos:'',
      descripcion:'',
      mostrar:false,
      socials: [{url:require('../assets/social/instagram.png'),name:"INSTAGRAM",link:"https://www.instagram.com"}, 
               {url:require('../assets/social/twitter.png'),name:"TWITTER",link:"https://www.twitter.com"}, 
               {url:require('../assets/social/linkedin.png'),name:"LINKEDIN",link:"https://www.linkedin.com"},
               {url:require('../assets/social/cactus.png'),name:"WEBSITE",link:"https://www.wearecactus.com"}
               ]
    }
  },
  methods:{
    guardar: function () {
      
    },
    borrar: function () {
      this.nombre='',
      this.apellidos='',
      this.descripcion=''
    },
    comprobarTexto: function(e){
      if ((this.nombre.length + this.apellidos.length + this.descripcion.length) > 0) {
        this.mostrar=true
      } else { this.mostrar=false }
    }
 }, components:{
   mensaje
 }
 }
</script>


<style scoped>
  .profile {    
    margin: auto;
    max-width: 1000px;
  }
  .ficha{
    float:left;
    max-width: 800px;
    padding: 10px;
    min-width: 800px;
  }
  .social{
    float: left;
    width: 180px;
    padding: 10px;
  }
  .contenedor{
    border: solid 1px #ccc;
    width: 100%;
    height: 440px;
    float: left;
    padding: 10px;
    border-radius: 5px;
  }
  .social img{
    float: right;
    max-width: 70px;
  }
  .social li{
    float:right;
    padding: 0 10px;
  }
  ul {
    list-style: none
  }
  .formNombre{
    float: left;
    width: 280px;
    margin: 0 0 10px 0;
  }
  .formApellidos{
    float: left;
    width: 480px;
    margin: 0 10px;
  }
  .formDescripcion{
    float: left;
    width: 770px;
    margin: 0 0 10px 0;
  }
  .btnGuardar{
    float: right;
    background-color: lightgreen;
  }
  .btnBorrar{
    float: right;
    margin: 5px;
    border: solid 1px #ccc;
    font-size: 12px;
  }
  .contenedor input{
    margin-bottom:20px;
    font-family: sans-serif;
    background-color: white;
  }
  .contenedor textarea{
    font-family: sans-serif;
    background-color: white;
  }
  
  .boton{
    float: left;
    width: 180px;
    padding: 10px;  
      
  }
  .btnGuardar{
    margin-top: 225;
    height: 80px;
    width: 100%;
  }
  .formulario{
    height: 300px;
    float: left;
    width: 1000px;
  }
  
  
  
  
</style>