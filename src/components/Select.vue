<script>
export default {
    
    data() {
       
    },
    methods: {
        enviar3() {
            this.$emit('Civ',this.civil)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot> {{ civil }}
        <br>
        <select
            v-model="civil"
            @change="enviar3"
            required
            
            class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0"
          >
            <option selected>Estado civil</option>
            <option value="1">Soltero</option>
            <option value="2">Casado</option>
            <option value="3">Divorciado</option>
            <option value="4">Separado</option>
            <option value="5">Union libre</option>
            <option value="6">Viudo</option>
          </select>
    </div>
</template>