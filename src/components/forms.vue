<script>
import caja from '../components/InputsText.vue';
import textar from '../components/textarea.vue'
import slider from '../components/InputSlider.vue';
import axios from "axios";
let API_URL = "/api/guardarPersonasUxd.php";

export default {
components:{
caja,textar,slider
  },
  emits: ['person','data','testa'],
  data() {
    return {
      nombre: "",
      edad: "",
      estadoCivil: "",
      trabajo: "",
      residencia: "",
      cita: "",
      citaAutor: "",
      bio: "",
      personalidad01: "0",
      personalidad02: "0",
      personalidad03: "0",
      personalidad04: "0",
      objetivos: [],
      frustraciones: [],
      motivaciones: [],
      porcentaje: "",
      marcas: "",
    };
  },

  methods: {

    nombreyapellido(s){
this.nombre=s;
      },
work(s){
this.trabajo=s;
      },
resi(s){
this.residencia=s;
      },
citas(s){
this.cita=s;
      },
citass(s){
this.citaAutor=s;
      },
biog(s){
this.bio=s;
      },
object(s){
this.objetivos=s;
      },
frustra(s){
this.frustraciones=s;
      },
slider1(s){
this.personalidad01=s;
      },
slider2(s){
this.personalidad02=s;
      },
slider3(s){
this.personalidad03=s;
      },
slider4(s){
this.personalidad04=s;
      },
motiv(s){
this.motivaciones=s;
      },
    submit() {
      axios
        .post(API_URL, {
          nombre: this.nombre,
          edad: this.edad,
          estadoCivil: this.estadoCivil,
          trabajo: this.trabajo,
          residencia: this.residencia,
          cita: this.cita,
          citaAutor: this.citaAutor,
          bio: this.bio,
          personalidad01: this.personalidad01,
          personalidad02: this.personalidad02,
          personalidad03: this.personalidad03,
          personalidad04: this.personalidad04,
          objetivos: this.objetivos,
          frustraciones: this.frustraciones,
          motivaciones: this.motivaciones,
          porcentaje: this.porcentaje,
          marcas: this.marcas,
        })
        .then((response) => {
          console.log(response.status);
        });
    },

  },
};
</script>

<template>
  <div class="font-sans">
    <div class="min-h-screen flex sm:justify-center " >
      <div style="margin: 100px 500px 100px 500px" class="rounded-xl px-6 py-4 bg-gray-100" >

          <h2 class="block mt-3 text-sm text-black text-center font-semibold text-xl">Registro de Usuario</h2>

        <form class="mt-20 w-96 flexo">

        <div class="Datos">  

          <div class="">
            <label for="nombre" class="block mb-2 text-sm font-medium  dark:text-white mt-7"><p class="text-black">Nombre y Apellido</p></label>
             <caja @data="nombreyapellido"></caja>
          </div>

          <div class="mt-7">
            <label for="edad" class="block mb-2 text-sm font-medium text-black dark:text-white mt-7"><p class="text-black">Edad</p></label>
            <input v-model="edad" type="number" placeholder="Edad" class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100 inn"/>
          </div>

          <label for="estadoCivil" class="block mb-2 text-sm font-medium text-black dark:text-white mt-7"><p class="text-black">Estado Civil</p></label>
          <select v-model="estadoCivil" class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100">
            <option selected>Estado civil</option>
            <option value="1">Soltero</option>
            <option value="2">Casado</option>
            <option value="3">Divorciado</option>
            <option value="4">Separado</option>
            <option value="5">Union libre</option>
            <option value="6">Viudo</option>
          </select>
          <div class="mt-7">
            <label for="trabajo" class="block mb-2 text-sm font-medium text-black dark:text-white mt-7"><p class="text-black">Trabajo</p></label>
            <caja @data="work"></caja>
        </div> 

          <div class="mt-7">
            <label for="residencia" class="block mb-2 text-sm font-medium text-black dark:text-white mt-7"
              ><p class="text-black">Residencia</p></label>
              <caja @data="resi"></caja>
          </div>

           

          
       

    
          <div class="mt-7">
            <label for="objetivos" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Objetivos</p></label>
            <caja @data="object"></caja>
          </div>
       

          <div class="mt-7">
            <label for="frustraciones" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Frustaciones</p></label>
            <caja @data="frustra"></caja>
          </div>
            </div>
<div class="Datos2">
          <div class="mt-7 slider">
          <label for="personalidad01" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Personalidad 1</p></label>
            <slider @person="slider1"></slider>
            <span>{{ this.personalidad01 }}%</span>
          </div>

          <div class="mt-7 slider">
            <label for="personalidad02" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Personalidad 2</p></label>
                <slider @person="slider2"></slider>
              <span>{{ this.personalidad02 }}%</span>
          </div>

          <div class="mt-7 slider">
            <label for="personalidad03" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Personalidad 3</p></label>
              <slider @person="slider3"></slider>
            <span>{{ this.personalidad03 }}%</span>
          </div>

          <div class="mt-7 slider">
          <label for="personalidad04" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Personalidad 4</p></label>
             <slider @person="slider4"></slider>
            <span>{{ this.personalidad04 }}%</span>
          </div>
         
        </div>
          <div class="mt-7">
            <label for="motivaciones" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Motivaciones</p></label>
            <caja @data="motiv"></caja>
          </div>
          <div class="mt-7">
            <label for="cita" class="block mb-2 text-sm font-medium text-black dark:text-white mt-7"><p class="text-black">Cita</p></label>
            <textar @testa="citas"></textar>
          </div>

          <div class="mt-7">
            <label for="citaAutor" class="block mb-2 text-sm font-medium text-black dark:text-white mt-7"><p class="text-black">Cita Autor</p></label>
            <textar @testa="citass"></textar>
          </div>

           <div class="mt-7">
            <label for="bio" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"><p class="text-black">Biografía</p></label>
            <textar @testa="biog"></textar>
          </div>

          <div class="mt-7">
            <label
              for="porcentaje"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"
              ><p class="text-black">Porcentaje</p></label
            >
            <input
              v-model="porcentaje"
              type="text"
              class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100 inn"/>
          </div>

          <div class="mt-7">
            <label
              for="marcas"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"
              ><p class="text-black">Marcas</p></label
            >
            <input
              v-model="marcas"
              type="text"
              class="mt-3 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100 inn"/>
          </div>
          <div>
            <button
              class="mt-7 bg-blue-500 w-full py-3 rounded-xl text-white shadow-xl hover:shadow-inner focus:outline-none transition duration-500 ease-in-out transform hover:-translate-x hover:scale-105"
              @click="submit()">
              Registrar
            </button>
          </div>
        
        </form>
      </div>
    </div>
  </div>
</template>
<style type="text/css">
  .Datos{
    display: inline-block;
    padding: 5px;
  }
   .Datos2{
    display: flex;
   }
   .slider{
    margin: 0px 10px 0px 5px;
   }
  .inn{
    text-align: center;
  }
</style>