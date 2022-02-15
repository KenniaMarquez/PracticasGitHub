<template>
    <div id="root">
        <input type = "text" placeholder="Escribe texto" v-on:keydown = "key">

        <h3 :style="[colorespecial]" v-if="keycode >=13 && keycode <=44">texto: {{keycode}}</h3>
        <h3 :style="[colornumero]" v-if="keycode >=47 && keycode <=58">texto: {{keycode}}</h3>
        <h3 :style="[colorletra]" v-if="keycode >=64 && keycode <=91">texto: {{keycode}}</h3>
        <h3 :style="[colorespecial]" v-if="keycode >=94 && keycode <=228">texto: {{keycode}}</h3>

    <h2 v-on:mousemove="getXY">{{title}}</h2>

    {{x}},{{y}}

    </div>
    
</template> 

<script>

export default {
        name:'FirstComponent',
        data(){
            return{
                title: 'Proyecto 2',
                x:0,
                y:0,
                keycode:''
            }
        },
        methods:{
            getXY(event){
                this.x=event.offsetX;
                this.y=event.offsetY;
            },

            key(event){
                this.keycode=event.keyCode
            }
        },
     computed:{
         colorletra(){
             return{
                 color:"green"
             }
         },
         colornumero(){
             return{
                 color:"red"
             }
         },
         colorespecial(){
             return{
                 color:"yellow"
             }
         }
     }
     
      
}
    

</script>
