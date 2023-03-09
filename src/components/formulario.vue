<script >
import btnn from '../components/btn.vue'
import axios from 'axios'
let API_URL = '/api/guardarPersonasUxd.php'

export default {

data(){
	return{
		nombre:'',
	}
},
components: {
    btnn
  },

methods: {
	enviar(){
		axios.post(API_URL, {
		nombre: this.nombre,
})
.then((response) => {
console.log(response.status)
});
	}
},

}  

</script>

<template>
<div class="formulario">
	<form class="object-center preguntas bg-teal-800" >
		<div class="objetos">
			<div class="formm">
			<label class="text-white" id="nombre" for="nombre">Nombre Completo:</label>
			<input type="text" id="nombre" v-model="nombre" class="border border-black w-80 p-1 text-center">
			</div>
		</div>
		<br>
		<div>
		<btnn class="bg-cyan-800 boton text-white hover:-translate-y-1 hover:scale-110 duration-300 hover:bg-orange-500">Enviar Formulario</btnn>
		</div>
	</form>
</div>

</template>

<style type="text/css">
	.formm{
		padding: 10px;
	}
	.preguntas{
		width: 80%;
		padding: 50px;
		text-align: center;
	}
	.formulario{
		text-align: center;
		align-items: center;
		margin: 10px 10px 10px 470px;
	}
	.boton{
		width: 80%;
		padding: 5px;
	}
</style>
