<script>
export default {
    props: ['desactivar'],
}
</script>
<template>
    <button :disabled="desactivar" class="mt-7 bg-blue-500 w-full py-3 rounded-xl text-white shadow-xl hover:shadow-inner focus:outline-none transition duration-500 ease-in-out transform hover:-translate-x hover:scale-105">
        <div class="flex gap-2 items-start justify-center">

            <slot></slot>
        </div>
    </button>
</template>