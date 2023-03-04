<script >
import axios from "axios";
let API_URL = "/api/guardarPersonasUxd.php";

export default {
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
            personalidad01: "",
            personalidad02: "",
            personalidad03: "",
            personalidad04: "",
            objetivos: [],
            frustraciones: [],
            motivaciones: [],
            porcentaje: "",
            marcas: "",
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
    },
};
</script>


<template>
    <div class=" text-center  place-item-center" style="margin: 10px 10px 10px 200px;">
        <card>
            <form class="w-full max-w-lg">
                <div grid grid-rows-4 grid-flow-col gap-4>

                    <div class="flex flex-wrap -mx-3 mb-2">
                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="nombre">
                                nombre completo:
                            </label>
                            <input v-model="nombre"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                                type="text" placeholder="escribe tu nombre completo" />
                        </div>

                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="edad">
                                edad:
                            </label>
                            <input v-model="edad"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                                type="tel" placeholder="tu edad" />
                        </div>

                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="estadocivil">
                                estado civil:
                            </label>
                            <select v-model="estadoCivil"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white">
                                <option value="1">soltero</option>
                                <option value="2">casado</option>
                                <option value="3">divorciado</option>
                                <option value="4">separado</option>
                                <option value="5">unión libre</option>
                                <option value="6">viudo</option>

                            </select>
                        </div>

                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="trabajo">
                                trabajo:
                            </label>
                            <input v-model="trabajo"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                                type="text" placeholder="trabajo">
                        </div>

                        <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="residencia">
                                residencia:
                            </label>
                            <input v-model="residencia"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                                type="text" placeholder="residencia">
                        </div>

                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="cita">
                                cita:
                            </label>
                            <input v-model="cita"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                                type="text" placeholder="cita">
                        </div>

                    </div>

                    <div class="flex flex-wrap -mx-3 mb-2">
                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="citaAutor">
                                cita autor:
                            </label>
                            <input v-model="citaAutor"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                                type="text" placeholder="cita de autor">
                        </div>
                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="bio">
                                bio:
                            </label>
                            <input v-model="bio"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                                type="text" placeholder="escribe tu biografia">
                        </div>


                        <div class="w-full md:w-1/3 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="personalidad01">
                                personalidad 1:
                            </label>
                            <input  
                                v-model="personalidad01" 
                                type="range" 
                                min="0" 
                                max="100" 
                                set="50"
                                class="w-full mb-5 h-3 rounded-lg mt-4 bg-gray-300 appearance-none focus:outline-none"/>
                                
                            <span class="absolute left-0 top-0 -mt-2 text-sm font-medium">Prospeccion</span>
                            <span class="absolute left-1/2 top-0 -mt-2 text-sm font-medium">{{
                                this.personalidad01
                            }}</span>
                            <span class="absolute right-0 top-0 -mt-2 text-sm font-medium">Juzgador</span>
                        </div>

                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="grid-first-name">
                                personalidad 2:
                            </label>
                            <input
                            v-model="personalidad04" type="range" min="0" max="100" set="50"
                                class="w-full mb-5 h-3 rounded-lg mt-4 bg-gray-300 appearance-none focus:outline-none" />
                                
                            <span class="absolute left-0 top-0 -mt-2 text-sm font-medium">Prospeccion</span>
                            <span class="absolute left-1/2 top-0 -mt-2 text-sm font-medium">{{
                                this.personalidad04
                            }}</span>
                            <span class="absolute right-0 top-0 -mt-2 text-sm font-medium">Juzgador</span>
                        </div>

                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="grid-last-name">
                                personalidad 3:
                            </label>
                            <input
                            v-model="personalidad04" type="range" min="0" max="100" set="50"
                                class="w-full mb-5 h-3 rounded-lg mt-4 bg-gray-300 appearance-none focus:outline-none" />
                                
                            <span class="absolute left-0 top-0 -mt-2 text-sm font-medium">Prospeccion</span>
                            <span class="absolute left-1/2 top-0 -mt-2 text-sm font-medium">{{
                                this.personalidad04
                            }}</span>
                            <span class="absolute right-0 top-0 -mt-2 text-sm font-medium">Juzgador</span>
                        </div>
                    </div>

                    <div class="flex flex-wrap -mx-3 mb-4">
                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="grid-first-name">
                                personalidad 4:
                            </label>

                            <input v-model="personalidad04" type="range" min="0" max="100" set="50"
                                class="w-full mb-5 h-3 rounded-lg mt-4 bg-gray-300 appearance-none focus:outline-none" />

                            <span class="absolute left-0 top-0 -mt-2 text-sm font-medium">Prospeccion</span>
                            <span class="absolute left-1/2 top-0 -mt-2 text-sm font-medium">{{
                                this.personalidad04
                            }}</span>
                            <span class="absolute right-0 top-0 -mt-2 text-sm font-medium">Juzgador</span>
                        </div>

                        <div class="w-full md:w-1/2 px-3">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="grid-last-name">
                                objetivos:
                            </label>
                            <input
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                                id="grid-last-name" type="text" placeholder="escribe tus apellidps">
                        </div>
                    </div>

                    <div class="flex flex-wrap -mx-3 mb-4">
                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="grid-first-name">
                                frustraciones:
                            </label>
                            <input
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                                id="grid-first-name" type="text" placeholder="escribe tu nombre">
                        </div>

                        <div class="w-full md:w-1/2 px-3">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                                for="grid-last-name">
                                motivaciones:
                            </label>
                            <input
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
                                id="grid-last-name" type="text" placeholder="escribe tus apellidps">
                        </div>
                    </div>

                    <div class="flex flex-wrap -mx-3 mb-4">
                        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
                            <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="marca">
                                marca:
                            </label>
                            <input v-model="marca"
                                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                                type="text" placeholder="escribe tu nombre">
                        </div>

                    </div>
                </div>

            </form>
        </card>
    </div>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="submit">
        Submit
    </button>
</template>
