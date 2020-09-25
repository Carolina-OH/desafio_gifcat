vue<template>
<div id="app">
    <div>
        <h1 class="text-center mt-5 mb-5"> Random Gif Cat</h1>
            <div id="form">
                <div class="p-5 card col-sm-6" id="card">
                        <div class="form-group row ml-2 pl-5">
                            <label class="col-sm-2 col-form-label">Titulo:</label>
                            <div class="col-sm-4">
                            <input type="text" class="form-control" v-model="tittle" ref="titulo">
                            </div>
                        </div>
                        <div class="form-group row ml-2 pl-5">
                            <label class="col-sm-2 col-form-label">Filtro:</label>
                            <div class="col-sm-4">
                             <select id="inputState" class="form-control" @change="cambioFiltro($event)">
                                <option v-for="opt in filtros" :key="opt" :value="opt" v-text="opt"></option>
                            </select>
                            </div>
                        </div>
                            <div class="form-group row ml-2 pl-5">
                                <label class="col-sm-2 col-form-label">Color:</label>
                                <div class="col-sm-4">
                                <select id="inputState" class="form-control" @change="cambioColor($event)">
                                   <!-- <option selected disabled>Choose...</option>!-->
                                    <option v-for="color in colors" :key="color.color" :value="color.value" v-text="color.color"></option>
                                </select>
                                </div>
                                <span :style="style" id="circle"></span>
                            </div>
                            <div class="form-group row ml-2 pl-5">
                                <label class="col-sm-2 col-form-label">Tamaño:</label>
                                <div class="col-sm-4">
                                <input type="text" class="form-control" v-model="size" ref="size">
                                </div>
                            </div>
                </div>
            </div>
                            <button @click="ObtenerGato">obtener mi gatito</button>
    </div>
                            <div class="text-center mb-5">
                                <img :src="url">
                            </div>

</div>
</template>

<script>
export default {
    name: 'randomgif',
    // props: {},
    data: function(){
        return {
            tittle:"",
            size:"",
             myFilter:{
                filter: "",
            },
            filtros:[
            "blur",
            "mono",
            "negative",
            "paint",
            "sepia",
            ],
            selected:"",
            url:"",
            colors:[
                {color:"Blanco", value:"white" },
                {color:"Verde", value:"green"},
                {color:"Rojo",value:"red"},
                {color:"Azul",value:"blue"},
                {color:"Amarillo",value:"yellow"},
                {color:"Morado",value:"purple"}

            ],
            style:{
                background:""
            }     
        }
    },
    // computed: {},
    methods: {
        cambioColor(e){
            this.style.background=e.target.value            
        },
            cambioFiltro(e){
            var response= e.target.value
            if(response==="blur"){
            this.selected="blur"
            
            console.log(this.selected)
            }else if(response==="mono"){
                this.selected="mono"
                console.log(this.selected)
                
            }else if(response==="negative"){
                this.selected="negative"
                console.log(this.selected)
              
            }else if(response==="paint"){
                this.selected="paint"
                console.log(this.selected)
               
            }else if(response==="sepia"){
                this.selected="sepia"
                console.log(this.selected)

            }
                return 
                selected,url
            },
            ObtenerGato(){
                if (this.size>100 || this.size<1 || isNaN(this.size)){
                    alert("Ingrese un número entre 1 y 100")
                    this.$refs.size.value=""
                    this.$refs.size.focus()
                }else if(this.tittle===""){
                        alert("Debe ingresar un titulo")
                        this.$refs.titulo.focus()
                }
                else
                this.url=`https://cataas.com/cat/gif/says/${this.tittle}?filter=${this.selected}&color=${this.style.background}&size=${this.size}&type=or`
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

    button{
        width:200px;
        margin-left:40%;
        margin-top:20px;
        margin-bottom:20px;
    }

</style>