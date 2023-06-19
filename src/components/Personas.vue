<script>
import axios from "axios";

let API_URL = '/api/getPersonasUxd.php';

export default {
  data() {
    return {
      info: [],
      personas: [],
      selectedId: null,
      dataPersona: null,
      modal:false,
    };
  },
  mounted() {
    axios.get(API_URL).then((response) => {
      this.personas = response.data.personas;
    });
  },
  methods: {
    saveId(id) {
      this.selectedId = id;
      let personaDataURL = API_URL + '?id=' + this.selectedId;
      axios.get(personaDataURL).then((response) => {
        this.dataPersona = response.data.persona;
        this.modal = true;
      });
    },
    cerrarModal(){
      this.modal=false;
    }
  },
};
</script>

<template>
  <ul  class="grid grid-cols-4 text-center" >
    <li type="button" 
        v-for="persona in personas" 
        class="card bg-[#A3BAB4] outline outline-black rounded-3xl m-5 scale-75 cursor-pointer hover:rotate-2" 
        @click="saveId(persona.id)">

        <img src="https://cdn-icons-png.flaticon.com/512/5249/5249427.png" alt="" @click="modal = true" >

      <div class="text-xl">{{ persona.nombre }}</div>
    </li>
  </ul>
  <Transition
    enter-active-class="ease-out duration-200"
    enter-class="opacity-0"
    enter-to-class="opacity-200"
    leave-active-class="ease-in duration-200"
    leave-class="opacity-100"
    leave-to-class="opacity-0"
  >
    <div
      class="relative z-10"
      aria-labelledby="modal-title"
      role="dialog"
      aria-modal="true"
      v-show="modal"
    >
      <div
        class="fixed inset-0 bg-green-700 bg-opacity-50 transition-opacity"
      ></div>
      <div class="fixed inset-0 z-10 overflow-y-auto">
        <div
          class="flex min-h-full items-end justify-center p-4 text-center sm:items-center sm:p-0"
        >
        <Transition
            enter-active-class="ease-out duration-300"
            enter-class="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
            enter-to-class="opacity-100 translate-y-0 sm:scale-100"
            leave-active-class="ease-in duration-200"
            leave-class="opacity-100 translate-y-0 sm:scale-100"
            leave-to-class="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
          >
            <div
            v-show="modal === true"
            v-if="dataPersona"
              class="bg-green-900 relative transform overflow-hidden rounded-3xl outline outline-blue-500 text-left shadow-xl transition-all sm:my-8 max-w-7xl"
            >
              <div class="bg-[#0aa6c1] px-4 pb-4 sm:p-6 sm:pb-4">
                <div class="sm:flex sm:items-start">
                  <div
                    class="mx-auto grid grid-rows-2 h-28 w-28 flex-shrink-0 items-center justify-center sm:mx-0 sm:h-28 sm:w-28"
                  >
                  
                    <a class="box bg-white text-2xl rounded-b-lg p-4 pt-0 pb-0 m-0 mt-30 text-center justify-center">Edad {{dataPersona.edad}}</a>
                
                  </div>
                  <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                    <h1
                      class="text-6xl text-center font-semibold leading-6 text-white"
                      id="modal-title"
                    >
                    {{ dataPersona.nombre}} 
                    <br>
                    <br>
                    </h1>
                    <div class="mt-2">
                    <h1 class="text-2xl text-center text-white">{{ dataPersona.trabajo }}</h1>
                    <br>
                    <h2 class="text-base text-white">Residencia: {{ dataPersona.residencia }}</h2>
                    <h2 class="text-base text-white">Cita: {{ dataPersona.cita }}</h2>
                    <h2 class="text-base text-white">Cita Autor: {{ dataPersona.citaAutor }}</h2>
                    <br>
                    <h2 class="text-base text-white">Biografia: {{ dataPersona.bio }}</h2>
                    <br>
                    <h2 class="text-lg text-white">Personalidad 1: {{ dataPersona.personalidad01 }}% Personalidad 2: {{ dataPersona.personalidad02 }}%</h2>
                     <h2 class="text-lg text-white">Personalidad 3: {{ dataPersona.personalidad03 }}% Personalidad 4: {{ dataPersona.personalidad04 }}%</h2>
                    <br>
                    <h2 class="text-lg text-white text-center">Objetivos</h2>
                    <br>
                     <div v-for="objetivo in dataPersona.objetivos" :key="objetivo.id">
                    <div class="text-base text-white text-center">*{{ objetivo.objetivo }}</div>

                    </div>
                    <br>
                    <h1 class="text-lg text-white text-center">Frustraciones</h1>
                    <br>

                    <div v-for="frustracion in dataPersona.frustraciones" :key="frustracion.id">
                      <div class="text-base text-white text-center">*{{ frustracion.frustracion }}</div>

                    </div>
                    <br>
                    <h1 class="text-lg text-white text-center">Motivaciones</h1>
                    <br>


                    <div v-for="motivacion in dataPersona.motivaciones" :key="motivacion.id">
                      <div class="text-base text-white text-center">*{{motivacion.motivacion }}</div>

                    </div>


                     
                    </div>
                  </div>
                </div>
                <div
                  class="bg-[#0aa6c1] px-4 py-3 sm:flex sm:flex-row sm:px-6 justify-end gap-40"
                >
                  <button
                    class="mt-3 inline-flex w-full justify-center rounded-3xl border border-gray-300 bg-green-700 px-4 py-2 text-base font-medium text-black shadow-sm hover:bg-red-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm"
                    @click="modal = false"
                    type="button"
                  >
                    Cerrar
                  </button>
                </div>
              </div>
            </div>
          </Transition>
        </div>
      </div>
    </div>
  </Transition>

</template>