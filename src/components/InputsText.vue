<script>
export default {
    
    data() {
        return {
            dialogo: ' '
        }
    },
    methods: {
        submit() {
            this.$emit('data',this.dialogo)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <br>
        <input type="text" class="mt-1 block w-full border-none bg-gray-100 h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100 inn" v-model="dialogo" @input="submit">

    </div>
</template>