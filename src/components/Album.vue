<template>
<section>
    <div class="container">
        <div class="row col-5">
            <div class="box m-3"></div>
            <div class="box m-3"></div>
            <div class="box m-3"></div>
            <div class="box m-3"></div>
            <div class="box m-3"></div>
        </div>
    </div>
</section>
</template>

<script>
export default {

}
</script>

<style lang="scss">
section{
    height: calc(100vh - 80px);
    background-color: #1E2D3B;

    .box{
        height: 50px;
        background-color: red;
    }
}
</style>