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
        <input type="number" placeholder="Edad" class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" v-model="dialogo" @input="submit">

    </div>
</template>