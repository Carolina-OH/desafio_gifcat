vue<template>
<div id="app">
    <div>
        <h1 class="text-center mt-5 mb-5"> Random Gif Cat</h1>
            <div id="form">
                <div class="p-5 card col-sm-6" id="card">
                        <div class="form-group row ml-5 pl-5">
                            <label class="col-sm-2 col-form-label">Titulo:</label>
                            <div class="col-sm-4">
                            <input type="text" class="form-control">
                            </div>
                        </div>
                        <div class="form-group row ml-5 pl-5">
                            <label class="col-sm-2 col-form-label">Filtro:</label>
                            <div class="col-sm-4">
                             <select id="inputState" class="form-control">
                                <option selected>Choose...</option>
                                <option>blur</option>
                                <option>mono</option>
                                <option>negative</option>
                                <option>paint</option>
                                <option>pixel</option>
                            </select>
                            </div>
                        </div>
                        <div class="form-group row ml-5 pl-5">
                            <label class="col-sm-2 col-form-label">Color:</label>
                            <div class="col-sm-4">
                             <select id="inputState" class="form-control">
                                <option selected>Choose...</option>
                                <option>Blanco</option>
                                <option>Rojo</option>
                                <option>Amarillo</option>
                                <option>Azul</option>
                                <option>Verde</option>
                                <option>Rosa</option>
                            </select>
                            </div>
                            <span>color</span>
                        </div>
                        <div class="form-group row ml-5 pl-5">
                            <label class="col-sm-2 col-form-label">Tamaño:</label>
                            <div class="col-sm-4">
                            <input type="text" class="form-control">
                            </div>
                        </div>
                    </div>
            </div>
        
    </div>
</div>
</template>

<script>
export default {
    name: 'randomgif',
    // props: {},
    data: function(){
        return {}
    },
    // computed: {},
    methods: {
        // -- Metodos
    },
    // components: {},
}
</script>

<style scoped>
    #form,#card{
    background-color:pink;
    }
    #card{
        border:none;
        margin-left:30%;
    }
    #circle{
        width:20px;
        background-color:green;
        display:inline-block;
    }
</style>