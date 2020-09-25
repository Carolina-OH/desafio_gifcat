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
                             <select id="inputState" v-model="sort" class="form-control" @change="cambioColor">
                                <option selected>Choose...</option>
                                <option>Blanco</option>
                                <option>Rojo</option>
                                <option>Amarillo</option>
                                <option>Azul</option>
                                <option>Verde</option>
                                <option>Rosa</option>
                            </select>
                            </div>
                            <span :class=
                            "[{redbg:this.rojo},
                            {whitebg:this.blanco},
                            {greenbg:this.verde},
                            {yellowbg:this.amarillo},
                            {bluebg:this.azul},
                            {pinkbg:this.rosa}
                            ]" id="circle"></span>
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
        return {
            sort:"",
            rojo:"",
            blanco:"",
            azul:"",
            verde:"",
            rosa:"",
            amarillo:"",
        }
    },
    // computed: {},
    methods: {
        cambioColor(){
            var data=this.sort;
            if(data ==="Rojo"){
            this.rojo=true
            this.blanco=false
            this.verde=false
            this.amarillo=false
            this.azul=false
            this.rosa=false
            }else if(data==="Blanco"){
                this.blanco=true
                this.rojo=false
                this.verde=false
                this.amarillo=false
                this.azul=false
                this.rosa=false
            }else if(data==="Verde"){
                this.verde=true
                
                this.blanco=false
                this.rojo=false
                this.amarillo=false
                this.azul=false
                this.rosa=false
            }else if(data==="Amarillo"){
                this.amarillo=true

                this.verde=false
                this.blanco=false
                this.rojo=false
                this.azul=false
                this.rosa=false
            }else if(data==="Azul"){
                this.azul=true

                this.amarillo=false
                this.verde=false
                this.blanco=false
                this.rojo=false
                this.rosa=false
            }else if(data==="Rosa"){
                this.rosa=true

                this.amarillo=false
                this.verde=false
                this.blanco=false
                this.rojo=false
                this.azul=false
                
            }
            
        }
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
        width:40px;
        display:inline-block;
        border-radius:100px 100px;
    }
    .redbg{
        background-color:red;
    }
    .whitebg{
        background-color:white;
    }
    .greenbg{
        background-color:green;
    }
    .yellowbg{
        background-color:yellow;
    }
    .bluebg{
        background-color:blue;
    }
    .pinkbg{
        background-color:#FF33DD;
    }

</style>