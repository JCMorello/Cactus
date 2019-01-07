<template>
  <div class="home">
    <div class="contenedor">
     
      <img v-bind:src="imagen"/>
            
      <div class="form">
        <div><label class="form-control-label" for="name">{{insertaNombre}}</label></div>
        <div><input id="name" name="name" class="form-control w3-input w3-border w3-round-large" type="text" v-model="name" v-on:keyup="comprobarTexto"></div>
        <div><button v-on:click="goToProfile()" class="btn btn-primary w3-button w3-round-large" v-bind:style="bgc">{{Entrar}}</button></div>
      </div>        
      
    </div>      
    
  </div>
</template>

<script>
 export default{
  name:'home',
  data() {
    return{
    insertaNombre: 'Inserta tu nombre',
    Entrar: 'Entrar',
    imagen: 'https://www.wearecactus.com/static/img/logo.png',
    mostrar:true,
    name: '',
    attemptSubmit: false,
    bgc: {
			backgroundColor: ''
		}
  }
  },
  methods:{
    validateForm: function () {
      if (this.name.length > 0) {
        this.bgc.backgroundColor = '#9fd356'
      } else {
        this.bgc.backgroundColor = '#f27979'
      }
    },
    comprobarTexto: function(e) {
      this.validateForm()
    },
    goToProfile() {
      if (this.name.length > 0) {
        this.$router.push({name:'profile'})
      }
    }
  }
 }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.contenedor{
  margin: auto;
  max-width: 500px;
  max-height: 300px;
  margin-top: 20%;
  font-family: calibri, sans-serif;
  color: gray;
}

.contenedor img{
  float:right;
}

.form{
  float: left;
  margin-top: 50px;
  width: 100%;
}

.form-control{
  width: 500px;
  margin: 5px 0;
}

.form button {
  background-color: lightgray;
  margin: 30px 30%;
  width: 40%;
  min-width: 120px;
  padding: 10px;
  font-size: x-large;
  font-weight: 300;
}

.form button:hover {
  color: gray;
}  
  
</style>
