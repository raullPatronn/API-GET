<script>
export default {
    
    data() {
        return {
            textoos: ' '
        }
    },
    methods: {
        submit() {
            this.$emit('testa',this.textoos)
        }
    }
}
</script>

<template>
    <div>
        <slot></slot>
        <br>
        <textarea type="text" class="mt-1 block w-full border-none text-black h-11 rounded-xl shadow-lg hover:bg-blue-100 focus:bg-blue-100 focus:ring-0 bg-teal-100 inn" v-model="textoos" @input="submit"></textarea>
        

    </div>
</template>