<template>
  <div class="p-hero"
       :style="{height: height+'px'}">
    <div class="p-sidebar">
      <div class="p-title">
        <h1>Portfolio</h1>
      </div>
      <div class="p-name">
        <h2>KazuwoKiwame12</h2>
      </div>
      <ul class="p-feature">
        <li>SoftwareEngineer</li>
        <li>Hav A Big Dream</li>
      </ul>
      <div class="design-bar"></div>
    </div>
  </div>
</template>

<script>
  export default {
    data: function () {
      return {
        height: 750
      }
    },
    methods: {
      handleResize: function() {
          this.height = window.innerHeight;
      }
    },
    created() {
      if (process.client) {
        window.addEventListener('resize', this.handleResize)
        this.handleResize()
      }
    },
    destroyed () {
      if (process.client) {
        window.removeEventListener('resize', this.handleResize)
      }
    },
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
    width: 35vw;
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
