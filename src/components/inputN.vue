<script>
export default {
    
    data() {
   
    },
    methods: {
        enviar1() {
            this.$emit('normal',this.inputN)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot> {{ inputN }}
        <br>
        <input class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0" type="text" v-model="inputN"  required @change="enviar1">

    </div>
</template>