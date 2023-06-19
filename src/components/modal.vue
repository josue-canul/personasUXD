<script>
export default{
    props:{
        modal:Boolean,
    }
}
</script>

<template>
  <Transition
    enter-active-class="ease-out duration-300"
    enter-class="opacity-0"
    enter-to-class="opacity-100"
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
        class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity"
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
              v-show="modal"
              class="relative transform overflow-hidden rounded-lg bg-white text-left shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-lg"
            >
              <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                <div class="sm:flex sm:items-start">
                  <div
                    class="mx-auto flex h-12 w-12 flex-shrink-0 items-center justify-center rounded-full bg-red-100 sm:mx-0 sm:h-10 sm:w-10"
                  >
                    <svg
                      class="h-6 w-6 text-red-600"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke-width="1.5"
                      stroke="currentColor"
                      aria-hidden="true"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M12 9v3.75m-9.303 3.376c-.866 1.5.217 3.374 1.948 3.374h14.71c1.73 0 2.813-1.874 1.948-3.374L13.949 3.378c-.866-1.5-3.032-1.5-3.898 0L2.697 16.126zM12 15.75h.007v.008H12v-.008z"
                      />
                    </svg>
                  </div>
                  <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                    <h3
                      class="text-base font-semibold leading-6 text-gray-900"
                      id="modal-title"
                    >
                      Deactivate account
                    </h3>
                    <div class="mt-2">
                      <p class="text-sm text-gray-500">
                        Are you sure you want to deactivate your account? All of
                        your data will be permanently removed. This action
                        cannot be undone.
                      </p>
                    </div>
                  </div>
                </div>
              </div>
              <div
                class="bg-gray-50 px-4 py-3 sm:flex sm:flex-row-reverse sm:px-6"
              >
                <button
                  type="button"
                  class="inline-flex w-full justify-center rounded-md border border-transparent bg-red-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-red-700 focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2 sm:ml-3 sm:w-auto sm:text-sm"
                >
                  Deactivate
                </button>
                <button
                  @click="modal = false"
                  type="button"
                  class="mt-3 inline-flex w-full justify-center rounded-md border border-gray-300 bg-white px-4 py-2 text-base font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm"
                >
                  Cancel
                </button>
              </div>
            </div>
          </Transition>
        </div>
      </div>
    </div>
  </Transition>
</template>

<script type="text/javascript">
  
import axios from 'axios'
let API_URL = `/api/getPersonasUxd.php`
export default {
  data() {
    return {
      persona: [],
      datos: {
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
        objetivos:[],
        objetivos2:[],
        objetivos3:[],
        objetivos4:[],
        frustraciones:[],
        frustraciones2:[],
        frustraciones3:[],
        frustraciones4:[],
        motivaciones: [],
        motivaciones2: [],
        motivaciones3: [],
        motivaciones4: [],
        porcentaje: "0",
        porcentaje2: "0",
        porcentaje3: "0",
        porcentaje4: "0",
        marcas: [],
        marcas2: [],
        marcas3: [],
        marcas4: [],

      },
      modal: false,
    };
  },
  mounted() {
    axios.get(API_URL)
      .then((response) => {
        this.persona = response.data.personas;
        console.log(response.data);
      })
  },

}
</script>

<template>

<!----modal-->
<Transition
    enter-active-class="ease-out duration-200"
    enter-class="opacity-0"
    enter-to-class="opacity-100"
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
        class="fixed inset-0 bg-gray-500 bg-opacity-50 transition-opacity"
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
              v-show="modal"
              class="bg-green-900 relative transform overflow-hidden rounded-3xl outline outline-blue-500 text-left shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-lg"
            >
              <div class="bg-green-900 px-4 pb-4 sm:p-6 sm:pb-4">
                <div class="sm:flex sm:items-start">
                  <div
                    class="mx-auto grid grid-rows-2 h-28 w-28 flex-shrink-0 items-center justify-center sm:mx-0 sm:h-28 sm:w-28"
                  >
                  
                    <a class="box bg-white rounded-b-3xl p-4 pt-0 pb-0 m-0 mt-16 text-center justify-center">Edad: {{this.datos.edad}}</a>
                
                  </div>
                  <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                    <h3
                      class="text-base font-semibold leading-6 text-white"
                      id="modal-title"
                    >
                    {{ this.datos.nombre}} 
                    <br>
                    <br>
                    </h3>
                    <div class="mt-2">
                      <p class="text-sm text-white"><strong> Trabajo: {{ this.datos.trabajo}} </strong></p> 
                      <p class="text-sm text-white"><strong> Residencia: {{ this.datos.residencia}}</strong></p>
                      <p class="text-sm text-white"><strong> Estado Civil: {{ this.datos.estadoCivil}}</strong></p>
                      <br>
                      <p class="text-sm text-white"><strong> Cita: {{ this.datos.cita}}</strong></p>
                      <br>
                      <p class="text-sm text-white"><strong> Cita Autor: {{ this.datos.citaAutor}}</strong></p>
                      <br>
                      <p class="text-sm text-white"><strong> Biografia: {{ this.datos.bio}}</strong></p>
                      <br>
                      <p class="text-sm text-white"><strong> Personalidad 1: {{ this.datos.personalidad01}}% Personalidad 2: {{ this.datos.personalidad02}}%</strong></p>
                      <p class="text-sm text-white"><strong> Personalidad 3: {{ this.datos.personalidad03}}% Personalidad 4: {{ this.datos.personalidad04}}%</strong></p>
                      <br>
                      <p class="text-sm text-white"><strong> Objetivos 2: {{ this.datos.objetivos2}}</strong></p>
                    </div>
                  </div>
                </div>
                <div
                  class="bg-green-900 px-4 py-3 sm:flex sm:flex-row sm:px-6 justify-end gap-40"
                >
                  <button
                    class="mt-3 inline-flex w-full justify-center rounded-3xl border border-gray-300 bg-white px-4 py-2 text-base font-medium text-black shadow-sm hover:bg-red-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm"
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
  <div>
    <ul class="grid grid-cols-4 text-center">
      <li
        @click="modal = true"
        type="button"
        class="card bg-[#A3BAB4] outline outline-pink-500 rounded-3xl m-5 scale-75 cursor-pointer hover:rotate-2"
        v-for="p in persona"
      >
        <img
          @click="(datos.nombre=p.nombre) &&(datos.edad=p.edad) &&(datos.trabajo=p.trabajo) &&(datos.residencia=p.residencia) &&(datos.estadoCivil=p.estadoCivil) &&(datos.cita=p.cita)
          &&(datos.citaAutor=p.citaAutor) &&(datos.bio=p.bio) &&(datos.personalidad01=p.personalidad01) &&(datos.personalidad02=p.personalidad02)
          &&(datos.personalidad03=p.personalidad03) &&(datos.personalidad04=p.personalidad04) &&(datos.objetivos2=p.objetivos2)"
          class="rounded-t-3xl"
          src= "https://www.losolivosbogota.com/sites/salas/form/imagenes/sin_imagen.png"
          alt="Imagen_Personaje"
        />
        <a @click="(datos.nombre=p.nombre) &&(datos.edad=p.edad) &&(datos.trabajo=p.trabajo) &&(datos.residencia=p.residencia) &&(datos.estadoCivil=p.estadoCivil) &&(datos.cita=p.cita)
        &&(datos.citaAutor=p.citaAutor) &&(datos.bio=p.bio) &&(datos.personalidad01=p.personalidad01) &&(datos.personalidad02=p.personalidad02)
        &&(datos.personalidad04=p.personalidad04) &&(datos.personalidad04=p.personalidad04) &&(datos.objetivos2=p.objetivos2)">{{ p.nombre }}</a>
      </li>
    </ul>
  </div>




</template>
<style>
   .boton{
    padding: 5px;
    border-radius:50%;
   }

  .textoimagen{
    display: inline-flex;
  }
  .info{
    display: block;
  }
  .informacion{
    float: right;
  }
  .caja{
    display: inline;
  }
  .box{
    padding: 20px;
  }
  .imgRedonda {
    width:300px;
    height:300px;
    border-radius:150px;
    border:10px color blue;
}

  
</style>