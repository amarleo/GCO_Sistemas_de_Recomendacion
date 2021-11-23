<template>
    <p>hola</p>
    <div id="readfile">
        <p>{{ message }}</p>
        <button v-on:click="readFile">Read File</button>
        <input type="file" name="inputfile" id="inputfile">

        <pre id="output"></pre>
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
        // readFile() {
        //     // var file = new File([""],"../../public/files/file1.txt");
        //     // var reader = new FileReader();
        //     // reader.readAsText(file);
        //     // reader.onload = function() {
        //     //     console.log(this.result);
        //     // }


            
        // },
    readFile() {
        document.getElementById("inputfile").addEventListener("change", function() {
            var reader = new FileReader();
            reader.onload = function() {
                var lines = this.result.split("\n");
                for(var i = 0; i < lines.length; i++) {
                    console.log(lines[i]);
                }
            }
            reader.readAsText(this.files[0]);
        })
    }
    }


}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
