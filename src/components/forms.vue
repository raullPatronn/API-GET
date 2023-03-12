<script>
import caja from '../components/InputsText.vue';
import textar from '../components/textarea.vue'
import slider from '../components/InputSlider.vue';
import inedad from '../components/inputedad.vue';
import axios from "axios";
let API_URL = "/api/guardarPersonasUxd.php";

export default {
components:{
caja,textar,slider,inedad,
  },
  emits: ['person','data','testa',],
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
old(s){
this.edad=s;
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

<div class="bg-gray-100 mx-auto max-w-6xl bg-white py-20 px-12 lg:px-24 shadow-xl mb-24">
  <form>
    <div class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4 flex flex-col">
   <!---Nombre y Edad ---> 
    <div class="datos -mx-3 md:flex mb-6">
      <div class="md:w-1/2 px-3 mb-6 md:mb-0">
        <label for="nombre" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Nombre y Apellido</label>
        <caja @data="nombreyapellido"></caja>
      </div>
      <!---Nombre y Edad --->
      <div class="md:w-1/2 px-3">
        <label for="edad" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Edad</label>
        <inedad @data="old"></inedad>
      </div>
    </div>
    <!--- Estado civil ---> 
    <label for="estadoCivil" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Estado Civil</label>
      <select v-model="estadoCivil" class="w-full bg-gray-200 border border-gray-200 text-black text-xs py-3 px-4 pr-8 mb-3 rounded">
        <option selected>Estado civil</option>
        <option value="1">Soltero</option>
        <option value="2">Casado</option>
        <option value="3">Divorciado</option>
        <option value="4">Separado</option>
        <option value="5">Union libre</option>
        <option value="6">Viudo</option>
      </select>
    <!---Los sliders ---> 
    <div class="sliders -mx-3 md:flex mb-6">
      <div class=" slider md:w-1/2 px-3 mb-6 md:mb-0">
        <label for="personalidad01" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Personalidad 1</label>
        <slider @person="slider1"></slider>
          <span>{{ this.personalidad01 }}%</span>
      </div>

      <div class=" slider md:w-1/2 px-3 mb-6 md:mb-0">
        <label for="personalidad02" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Personalidad 2</label>
          <slider @person="slider2"></slider>
            <span>{{ this.personalidad02 }}%</span>
      </div>

      <div class=" slider md:w-1/2 px-3 mb-6 md:mb-0">
        <label for="personalidad03" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Personalidad 3</label>
        <slider @person="slider3"></slider>
          <span>{{ this.personalidad03 }}%</span>
      </div>

      <div class=" slider md:w-1/2 px-3 mb-6 md:mb-0">
        <label for="personalidad04" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Personalidad 4</label>
        <slider @person="slider4"></slider>
          <span>{{ this.personalidad04 }}%</span>
      </div>
    </div>
      <div class="datos2 -mx-3 md:flex mb-6">
        <!--- cita ---> 
        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
          <label for="cita" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Cita</label>
          <textar @testa="citas"></textar>
        </div>
        <!--- autor ---> 
        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
          <label for="citaAutor" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Cita Autor</label>
          <textar @testa="citass"></textar>
        </div>
        <!--- Biografia ---> 
        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
          <label for="bio" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Biografía</label>
          <textar @testa="biog"></textar>
        </div>
      </div>
      <div class="datos3 -mx-3 md:flex mb-6">
        <!--- Motivaciones ---> 
        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
          <label for="motivaciones" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Motivaciones</label>
          <caja @data="motiv"></caja>
        </div>
        <!--- Porcentaje ---> 
        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
          <label for="porcentaje" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Porcentaje</label>
          <input v-model="porcentaje" type="text" class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3"/>
        </div>
        <!--- Marcas---> 
        <div class="md:w-1/2 px-3 mb-6 md:mb-0">
          <label for="marcas" class="uppercase tracking-wide text-black text-xs font-bold mb-2">Marcas</label>
          <input v-model="marcas" type="text" class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3"/>
        </div>
          <br>

            
    </div>
    <div class="-mx-3 md:flex mt-2">
      <div class="md:w-full px-3">
        <button class="md:w-full bg-teal-800 text-white font-bold py-2 px-4 border-b-4 hover:border-b-2 border-gray-500 hover:border-gray-100 rounded-full" @click="submit()">Registrar</button>
      </div>
    </div>
    </div>
  </form>
</div>
</template>