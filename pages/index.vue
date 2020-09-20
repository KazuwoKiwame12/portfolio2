<template>
  <div class="main-container">
    <div style="background-color: black;">
      <div class="element-container">
        <service/>
      </div>
    </div>
    <div style="background-color: white;">
      <div class="element-container">
        <div style="height: 100px; width: 100%;"></div>
        <div class="design-bar"></div>
      </div>
    </div>
    <blog/>
    <div style="background-color: black;">
      <div class="element-container">
        <div style="height: 50px; width: 100%; border-left: solid 3px white;"></div>
      </div>
    </div>
    <div style="background-color: white;">
      <div class="element-container">
        <img @click="scrollTop" src="/toTop.png" alt="no-image" style="margin: 10px auto; width: 100px; height: 30px;"/>
      </div>
    </div>
  </div>
</template>

<script>
  import service from './service_el'
  import blog from './blog_el'

  export default {
    components: {
      service,
      blog
    },
    methods: {
      scrollTop() {
        window.scrollTo({
          top: 0,
          behavior: "smooth"
        })
      }
    }
  }
</script>

<style scoped>
  .main-container {
    width: 100vw;
  }
  .element-container {
    width: 80%;
    margin: 0 auto;
  }

  .design-bar {
    width: 100%;
    height: 300px;
    border-left: solid 3px black;
  }
</style>
