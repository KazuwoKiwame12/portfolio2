<template>
  <header class="p-header">
    <div class="p-container">
      <nav class="p-nav">
        <!--リンクにする-->
        <div class="nav-item">
          <span>about</span>
        </div>
        <div class="nav-item">
          <span>work</span>
        </div>
        <div class="nav-item">
          <span>word</span>
        </div>
        <div class="nav-item">
          <span>blog</span>
        </div>
        <div class="nav-item">
          <span>contact</span>
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
</script>

<style scoped>
  .p-header {
    position: absolute;
    top: 120px;

    color: white;
    height: 70px;
    width: 100vw;

    display: flex;
    justify-content: center;
  }

  .p-container {
    margin: 0 auto;
    width: 80%;

    display: flex;
    justify-content: flex-end;
  }

  .p-nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 50%;
    font-weight: 300;
    font-size: 24px;
  }

  .nav-item{
    text-align: center;
  }
</style>
