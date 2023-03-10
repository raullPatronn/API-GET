<script>
export default {
    
    data() {
        return {
            slider: 25
        }
    },
    methods: {
        enviar() {
            this.$emit('person',this.slider)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot> ({{ slider }}%)
        <br>
        <input type="range" class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100 " min="0" max="100" v-model="slider" @change="enviar">

    </div>
</template>