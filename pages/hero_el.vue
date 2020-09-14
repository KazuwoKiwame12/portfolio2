<template>
  <div id="work-trigger" class="p-hero">
    <div class="p-sidebar">
      <div class="p-title">
        <h1>Portfolio</h1>
      </div>
      <div id="work-content" style="opacity: 0; transform: translateX(-100%)">
        <div class="p-name">
          <h2>KazuwoKiwam12</h2>
        </div>
        <ul class="p-feature">
          <li>SoftwareEngineer</li>
          <li>Have a big dream</li>
        </ul>
        <div class="design-bar"></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    mounted() {
      const scene1 = this.$scrollmagic
        .scene({
          triggerElement: '#work-trigger',
          triggerHook: 0,
          duration: 400,
          reverse: false
        })
        .setTween('#work-content', {
          css: {
            opacity: '1',
            transform: 'translateX(0)'
          }
        })

      this.$scrollmagic.addScene(scene1)
    }
  }
</script>

<style scoped>
  .p-hero {
    background: url('/hero.JPG');
    background-size: cover;
    height: 750px;
    width: 100vw;
  }

  .p-sidebar {
    height: 100%;
    width: 325px;
    background-color: black;
    opacity: 0.95;
    color: white;
  }

  .p-title {
    font-weight: 300;
    font-size: 48px;
    position: relative;
    top: 110px;
    text-align: center;
  }

  .p-name {
    font-weight: normal;
    font-size: 36px;
    position: relative;
    top: 150px;
    left: 30%;
  }

  .p-feature {
    font-weight: normal;
    font-size: 48px;
    line-height: 64px;
    position: relative;
    top: 200px;
    left: 30%;
  }

  .design-bar {
    position: relative;
    top: 230px;
    left: 30%;
    width: 35vw;

    border-color: white;
    border-bottom: solid 3px;
  }
</style>
