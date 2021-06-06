<template lang="fr">
<div class="content">
    <Circle  :type="player" :url="url" :color="color" />
    <p class="result">{{result}}</p>
    <Circle  :type="ia.type" :url="ia.url" :color="ia.color" />
</div>
</template>
<script>
import Circle from "../components/Circle";

export default {
    name: 'Battle',
    components:{
        Circle,
    },
    props:{
        ia: {},
        player: String,
        result:String,
        url:String,
        color:String
    },

    data(){
        return {
             style: {
                '--color': this.color,
            },  
    
                
        }        
    },

    methods: {
        
    }

   
    
}

</script>
<style scoped>

    .circle{
        width: 10vw;
        height: 10vw;
        border-radius: 100%;
        border: 2vw solid var(--color);
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: white;
    }
    .content{
        display: flex;
        align-items: center;
        flex-direction: row!important;
        justify-content: space-between!important;
    }
    .icon{
        width: 40%;
    }

    .result{
        font-size: 30px;
        font-weight: bold;
        text-transform: uppercase;
        color: white;
    }


</style>