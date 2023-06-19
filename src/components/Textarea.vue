<script>
export default {
    
    data() {
       
    },
    methods: {
        enviar2() {
            this.$emit('tare',this.tarea)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot> {{ tarea }}
        <br>
        <textarea class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0" type="text" v-model="tarea" required @change="enviar2"></textarea>
    </div>
</template>