<template>
    <p>hola</p>
    <div id="readfile">
        <p>{{ message }}</p>
        <button v-on:click="readFile">Read File</button>
    </div>
</template>

<script>
// import Vue from 'vue';
// window.Vue = Vue;

export default {

    data() {
        return {
            message: 'Hola'
        }
    },
    methods: {
        readFile() {
            this.message = this.message.split('').reverse();
        }
    }

}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
