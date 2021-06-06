<template lang="fr">
    <div class="circle" :style="style" v-on:click='action'>
        <img class="icon" :src="require('@/assets/' + url + '')"> 
    </div>
</template>
<script>

export default {
    name: 'Circle',
    props:{
        url: String,
        color: String,
        type:String,
        random:String,
    },

    data(){
        return {
             style: {
                '--color': this.color,
            },  

                
                
        }        
    },

    methods: {


        action: function(){

    
            if(this.type == this.random){
                this.$emit('clicked',this.type,this.random,'Egalité',this.color,this.url)
                    
                
            }
            else if (this.type=='Papier' && this.random == 'Pierre'){
                this.$emit('clicked',this.type,this.random,'win',this.color,this.url)
            }
             else if (this.type=='Papier' && this.random == 'Ciseaux'){
                this.$emit('clicked',this.type,this.random,'lose',this.color,this.url)
            }

            else if (this.type=='Ciseaux' && this.random == 'Pierre'){
                this.$emit('clicked',this.type,this.random,'lose',this.color,this.url)
            }
             else if (this.type=='Ciseaux' && this.random == 'Papier'){
                this.$emit('clicked',this.type,this.random,'win',this.color,this.url)
            }

            else if (this.type=='Pierre' && this.random == 'Ciseaux'){
                this.$emit('clicked',this.type,this.random,'win',this.color,this.url)
            }
             else if (this.type=='Pierre' && this.random == 'Papier'){
                this.$emit('clicked',this.type,this.random,'lose',this.color,this.url)
            }

        }
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

    .icon{
        width: 40%;
    }


</style>