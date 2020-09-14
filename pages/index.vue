<template>
  <div id="work-trigger-service" class="main-container">
    <div style="background-color: black;">
      <div class="element-container">
        <service id="work-service" style="opacity: 0; transform: translateX(-100%)"/>
      </div>
    </div>
    <div id="work-trigger-blog" style="background-color: white;">
      <div class="element-container">
        <div style="height: 100px; width: 100%;"></div>
        <div id="work-blog-attach" class="design-bar" style="opacity: 0; transform: translateX(100%)"></div>
      </div>
    </div>
    <blog id="work-blog" style="opacity: 0; transform: translateX(100%)"/>
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
    mounted() {
      const scene1 = this.$scrollmagic
        .scene({
          triggerElement: '#work-trigger-service',
          triggerHook: 1,
          duration: 1000,
          reverse: false
        })
        .setTween('#work-service', {
          css: {
            opacity: '1',
            transform: 'translateX(0)'
          }
        })

      const scene2 = this.$scrollmagic
        .scene({
          triggerElement: '#work-trigger-blog',
          triggerHook: 1,
          duration: 1500,
          reverse: false
        })
        .setTween('#work-blog-attach', {
          css: {
            opacity: '1',
            transform: 'translateX(0)'
          }
        })

      const scene3 = this.$scrollmagic
        .scene({
          triggerElement: '#work-trigger-blog',
          triggerHook: 1,
          duration: 1500,
          reverse: false
        })
        .setTween('#work-blog', {
          css: {
            opacity: '1',
            transform: 'translateX(0)'
          }
        })

      this.$scrollmagic.addScene(scene1)
      this.$scrollmagic.addScene(scene2)
      this.$scrollmagic.addScene(scene3)
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
