<template>
    <div class="resultBlock">
    <p>Your time is {{ this.showResult }} ms</p>
    <p>{{ this.rank }}</p>
    </div>
</template>

<script>
export default{
    props:['showResult'],
    data(){
        return{
            rank:null
        }
    },
    methods:{
         ranking(){
            if(this.showResult < 250){
                this.rank = "Fast AF Boi"
            }else if(this.showResult < 400){
                this.rank = "Sick Reflexes Bro"
            }else{
                this.rank = "Old man fingers"
            }
        }
    },
    mounted(){
        this.ranking();
    },
}
</script>
<style>
.resultBlock p{
    font-size: 1.4rem;
    color: turquoise;
    font-weight: bold;
}
</style>