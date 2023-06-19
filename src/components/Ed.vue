<script>
export default {
    
    data() {
   
    },
    methods: {
        enviar4() {
            this.$emit('num',this.numero)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot> {{ numero }}
      
        <input class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0" type="number" v-model="numero" required @change="enviar4">
      
    </div>
</template>