<template>
<section>
    <div class="container">
        <div class="row">
            <div v-for="(cover,index) in arrayDischi" :key="index" class="box m-3 col-2">
                <Disco :dettagli="cover"/>
            </div>
        </div>
    </div>
</section>
</template>

<script>
import axios from 'axios';
import Disco from '@/components/Disco.vue'
export default {
    name: 'Album',
    components:{
        Disco
    },
    data(){
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            arrayDischi: ''
        }
    },
    created(){
        this.dischi();
    },
    methods:{
        dischi(){
            axios
                .get(this.apiUrl)
                .then(risposta => {
                   this.arrayDischi = risposta.data.response;
                   console.log(this.arrayDischi);
                })
        }
    }
}
</script>

<style lang="scss">
section{
    height: calc(100vh - 80px);
    background-color: #1E2D3B;
    .box{
        height: 300px;
    }
}
</style>