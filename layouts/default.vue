<template>
  <div class="setting">
    <c-header/>
    <c-hero/>
    <Nuxt/>
    <c-footer/>
  </div>
</template>

<script>
  import cHeader from '~/components/header'
  import cFooter from '~/components/footer'
  import cHero from '~/pages/hero_el'

  export default {
    components: {
      cHeader,
      cFooter,
      cHero
    }
  }
</script>
<style>
  .setting {
    font-family: Baskerville,serif;/*他のフォントも試す*/
    font-style: italic;
  }
  /*.container {*/
  /*  width: 100vw;*/
  /*  background-color: black;*/
  /*}*/
</style>
