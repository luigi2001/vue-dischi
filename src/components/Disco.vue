<template>
  <section>
      <img :src="dettagli.poster" :alt="dettagli.title">
      <h3 class="m-2 text-center">{{dettagli.title}}</h3>
      <p class="m-2 text-center">
          {{dettagli.author}}
          {{dettagli.year}}
      </p>
  </section>
</template>

<script>
export default {
    name: 'Disco',
    props:["dettagli"]
}
</script>

<style lang="scss">
img{
    width: 100%;
}
h3{
    color: white;
}
p{
    color: gray;
}
</style>