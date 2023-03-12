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
        <textarea type="text" class="w-full bg-gray-200 text-black border border-gray-200 rounded py-3 px-4 mb-3" v-model="textoos" @input="submit"></textarea>
        

    </div>
</template>