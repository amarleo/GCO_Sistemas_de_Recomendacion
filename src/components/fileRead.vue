<template>
    <p>hola</p>
    <div id="readfile">
        <p>{{ message }}</p>
        <input type="file" name="inputfile" id="inputfile">
        <button v-on:click="readFile">Read File</button>
        

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
                var matrix;
                var matrix_content;
                reader.onload = function() {
                    var lines = this.result.split("\n");

                    matrix = new Array(lines.length).fill(0).map(() => new Array(lines.length).fill(0));
                    for(var i = 0; i < lines.length; i++) {
                        matrix_content = lines;
                        matrix_content = this.result.split(/\s+/);
    
                        for (var j = 0; j < matrix_content.length / lines.length; j++) {
                            // OJO: AQUI CAMBIO DE STRING A INT
                            matrix[i][j] = parseInt(matrix_content[(lines.length * i) + j]);
                        }
                    }
                    console.log(matrix);
                }

                reader.readAsText(this.files[0]);
            })
        },




    }


}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
