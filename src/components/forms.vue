<script>
import axios from "axios";
let API_URL = "/api/guardarPersonasUxd.php";

export default {
  data() {
    return {
      nombre: "",
      edad: "",
      estadoCivil: "",
      
    };
  },

  methods: {
    submit() {
      axios
        .post(API_URL, {
          nombre: this.nombre,
          edad: this.edad,
          estadoCivil: this.estadoCivil,
        
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
          <div class="">
            <label for="nombre" class="block mb-2 text-sm font-medium  dark:text-white mt-7"><p class="text-black">Nombre y Apellido</p></label>
            <input v-model="nombre" type="text" placeholder="Raul Patron" class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100"/>
          </div>

          <div class="mt-7">
            <label for="edad" class="block mb-2 text-sm font-medium text-black dark:text-white mt-7"><p class="text-black">Edad</p></label>
            <input v-model="edad" type="number" placeholder="Edad" class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100"/>
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

          
          </div>
          <div>
            <button
              class="mt-7 bg-blue-500 w-full py-3 rounded-xl text-white shadow-xl hover:shadow-inner focus:outline-none transition duration-500 ease-in-out transform hover:-translate-x hover:scale-105"
              @click="submit()"
            >
              Registrar
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<style type="text/css"></style>