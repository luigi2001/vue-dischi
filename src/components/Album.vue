<template>
<div class="album">
    <div class="container position-relative" v-if="!loading">
        <div class="row p-5">
            <div v-for="(cover,index) in arrayDischi" :key="index" class="box m-3 p-2 col-2">
                <Disco :dettagli="cover"/>
            </div>
        </div>
    </div>
    <div v-else class="preloader_1 position-absolute top-50 start-50 translate-middle">
        <span class="d-block position-absolute"></span>
        <span class="d-block position-absolute"></span>
        <span class="d-block position-absolute"></span>
        <span class="d-block position-absolute"></span>
        <span class="d-block position-absolute"></span>
    </div>
</div>
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
            arrayDischi: '',
            loading: true
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
                   this.loading = false;
                })
        }
    }
}
</script>

<style lang="scss">
.album{
    height: calc(100vh - 80px);
    background-color: #1E2D3B;

    .box{
        background-color: #2E3A46;
    }

    .preloader_1{
        span{
            bottom:0px;
            width: 9px;
            height: 5px;
            background:#9b59b6;
            animation: preloader_1 1.5s  infinite ease-in-out;

            &:nth-child(2){
                left:11px;
                animation-delay: .2s;
            }
            &:nth-child(3){
                left:22px;
                animation-delay: .4s;
            }
            &:nth-child(4){
                left:33px;
                animation-delay: .6s;
            }
            &:nth-child(5){
                left:44px;
                animation-delay: .8s;
            }
        }
    }
}
@keyframes preloader_1 {
    0% {height:5px;transform:translateY(0px);background:#9b59b6;}
    25% {height:30px;transform:translateY(15px);background:#3498db;}
    50% {height:5px;transform:translateY(0px);background:#9b59b6;}
    100% {height:5px;transform:translateY(0px);background:#9b59b6;}
}
</style>