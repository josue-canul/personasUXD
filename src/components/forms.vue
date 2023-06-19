<script>
import axios from "axios";
import botonE from '../components/boton.vue';
import inpuS from '../components/slider.vue';
import Normal from '../components/inputN.vue';
import Texta from '../components/Textarea.vue';
import Selec from '../components/Select.vue';
import Nume from '../components/Ed.vue';
let API_URL = "/api/guardarPersonasUxd.php";
export default {
  components: {botonE, inpuS, Normal, Texta, Selec, Nume
},
  emits: ['person'], emits: ['normal'], emits: ['tare'], emits: ['Civ'], emits: ['num'],
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
      
      habilitar: false,
    };
  },
  methods: {
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
    pers1(s){
                this.personalidad01=s;
                console.log(s);
            },
    pers2(s){
                this.personalidad02=s;
                console.log(s);
            },
    pers3(s){
                this.personalidad03=s;
                console.log(s);
            },
    pers4(s){
                this.personalidad04=s;
                console.log(s);
            },
    nombres(s){
                this.nombre=s;
                console.log(s);
            },
    residen(s){
                this.residencia=s;
                console.log(s);
            },
    traba(s){
                this.trabajo=s;
                console.log(s);
            },
    tareas(s){
                this.cita=s;
                console.log(s);
            },
    Autor(s){
                this.citaAutor=s;
                console.log(s);
            },
    Biogra(s){
                this.bio=s;
                console.log(s);
            },
    EstadoC(s){
                this.estadoCivil=s;
                console.log(s);
            },
    Nu(s){
                this.edad=s;
                console.log(s);
            },
    objetivo1(s){
                this.objetivos2=s;
                this.objetivos=[{value:s}];
                console.log(this.objetivos)
            },
    objetivo2(s){
                this.objetivos3=s;
                this.objetivos=[{value: this.objetivos2},{value: this.objetivos3}];
                console.log(this.objetivos3)
            },
    objetivo3(s){
                this.objetivos4=s;
                this.objetivos=[{value: this.objetivos2},{value: this.objetivos3},{value: this.objetivos4}];
                console.log(this.objetivos4)
                console.log(this.objetivos)
            },
    frustracion1(s){
                this.frustraciones2=s;
                this.frustraciones=[{value:s}];
                console.log(this.frustraciones)
            },
    frustracion2(s){
                this.frustraciones3=s;
                this.frustraciones=[{value: this.frustraciones2},{value: this.frustraciones3}];
                console.log(this.frustraciones3)
            },
    frustracion3(s){
                this.frustraciones4=s;
                this.frustraciones=[{value: this.frustraciones2},{value: this.frustraciones3},{value: this.frustraciones4}];
                console.log(this.frustraciones4)
                console.log(this.frustraciones)
            },
    motivacion1(s){
                this.motivaciones2=s;
                
            },
    motivacion2(s){
                this.motivaciones3=s;
            
            },
    motivacion3(s){
                this.motivaciones4=s;
            },
    por1(s){
                this.porcentaje2=s;
                this.motivaciones={value: this.motivaciones2,'porcentaje':s};
                console.log(this.motivaciones)
            },
    por2(s){
                this.porcentaje3=s;
                this.motivaciones=[{value: this.motivaciones2,'porcentaje':this.porcentaje2},{value: this.motivaciones3, 'porcentaje':s}];
                console.log(this.motivaciones);
             
            },
    por3(s){
                this.porcentaje4=s;
                this.motivaciones=[{value: this.motivaciones2,'porcentaje':this.porcentaje2},{value: this.motivaciones3, 'porcentaje':this.porcentaje3},{value: this.motivaciones4, 'porcentaje':s}]
                console.log(this.motivaciones)
            }
    
    
  },
};
</script>

<template>
  <div class="font-sans">
    <div class="min-h-screen flex sm:justify-center bg-cyan-600" >
      <div
        style="margin: 100px 10px 100px 10px"
        class="rounded-3xl px-6 py-4 bg-teal-400 border"
      >
        <label
          for=""
          class="block mt-3 text-sm text-gray-700 text-center font-bold"
        >
          Registro de personas ISCLAB
        </label>
        <form class="mt-20 w-96">
          
          <div class="mt-7">
            <Normal @normal="nombres">Escribe nombre completo</Normal>


          </div>

          <div class="mt-7">
            <Selec @Civ="EstadoC">Estado Civil</Selec>
           
          </div>

          <div class="mt-7">
            <Nume @num="Nu">Edad</Nume>
        

          </div>

          <div class="mt-7">
            <Normal @normal="residen">Escribe tu residencia</Normal>
          </div>

          <div class="mt-7">
            <Normal @normal="traba">Escribe donde trabajas</Normal>
           
          </div>

          <div class="mt-7">
            <Texta @tare="tareas">Escribe tu cita</Texta>
          </div>

          <div class="mt-7">
            <Texta @tare="Autor">Escribe tu cita Autor</Texta>
            
          </div>
          <div class="mt-7">
            <Texta @tare="Biogra">Escribe tu biografia</Texta>
          </div>

          <div class="mt-7">
            <inpuS @person="pers1">Personalidad 01</inpuS>

         
          </div>

          <div class="mt-7">
            <inpuS @person="pers2">Personalidad 02</inpuS>
            
          </div>

          <div class="mt-7">
            <inpuS @person="pers3">Personalidad 03</inpuS>
            
          </div>

          <div class="mt-7">
            <inpuS @person="pers4">Personalidad 04</inpuS>
            
          </div>

          <div class="mt-7">
            <Normal @normal="objetivo1">Escribe 3 Objetivos:</Normal>
          </div>
          <div class="mt-1">
            <Normal @normal="objetivo2"></Normal>
          </div>

          <div class="mt-1">
            <Normal @normal="objetivo3"></Normal>
          </div>

          <div class="mt-7">
            <Normal @normal="frustracion1">Escribe 3 Frustraciones:</Normal>
          </div>
          <div class="mt-1">
            <Normal @normal="frustracion2"></Normal>
          </div>

          <div class="mt-1">
            <Normal @normal="frustracion3"></Normal>
          </div>

          <div class="mt-7">
            <Normal @normal="motivacion1">Escribe 3 Motivaciones:</Normal>
          </div>

          <div class="mt-1">
            <inpuS @person="por1"></inpuS>
          </div>

          <div class="mt-1">
            <Normal @normal="motivacion2"></Normal>
          </div>

          <div class="mt-7">
            <inpuS @person="por2"></inpuS>
          </div>

          <div class="mt-1">
            <Normal @normal="motivacion3"></Normal>
          </div>

          <div class="mt-7">
            <inpuS @person="por3"></inpuS>
          </div>

         

          <div class="mt-7">
            <label
              for="marcas"
              class="block mb-2 text-sm font-medium text-gray-900 dark:text-white mt-7"
              >Marcas</label
            >
            <input
              v-model="marcas"
              type="text"
              class="mt-3 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0"
            />
          </div>
          <div>
            
          </div>
          <botonE :desactivar="habilitar"  @click="submit"> Enviar</botonE>
        </form>
      </div>
    </div>
  </div>
</template>