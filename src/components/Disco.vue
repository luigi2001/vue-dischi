<template>
  <section class="m-5">
      <img :src="dettagli.poster" :alt="dettagli.title">
      <h3>{{dettagli.title}}</h3>
      <p>
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
    width: 200px;
}

</style>