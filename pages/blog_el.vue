<template>
  <div class="p-blog">
    <div class="title-container">
      <h1 class="p-title">Blog</h1>
      <p class="p-subtitle">intoroduce about things I studies</p>
    </div>
    <div style="background-color: black">
      <div class="blog-container">
        <h2 class="blog-title" style="text-align: right;">frontend</h2>
        <div class="blog-container_frontend" >
          <img @click="nextBlogFront" class="navigate-icon" src="/next_frontend.png" alt="no-image"/>
          <div class="blog-icon my-8" v-for="(frontend, index) in images_frontend">
            <blog-circle :image="frontend"/>
          </div>
        </div>
        <h2 class="blog-title relative bg-black" style="text-align: left; top: -3rem; max-width: 200px;">
          backend
        </h2>
        <div class="blog-container_backend" >
          <div class="blog-icon mb-8" v-for="(backend, index) in images_backend">
            <blog-circle :image="backend"/>
          </div>
          <img @click="nextBlogBack" class="navigate-icon" src="/next_backend.png" alt="no-image"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import blogCircle from '~/components/blog_circle'
    export default {
        components :{
          blogCircle
        },
        data() {
          return {
            images_frontend: [
              "nuxt.png",
              "swift.png",
              "java.png"
            ],
            images_backend: [
              "golang.png",
              "node.png",
              "laravel.png"
            ]
          }
        },
        methods: {
          nextBlogFront() {
            const firstElement = this.images_frontend.shift();
            this.images_frontend.push(firstElement)
          },
          nextBlogBack() {
            const firstElement = this.images_backend.reverse().shift();
            this.images_backend.push(firstElement)
            this.images_backend.reverse();
          }
        }
    }
</script>

<style scoped>
  .title-container {
    text-align: center;
    width: 80%;

    margin: 0 auto;

    border-top: 3px solid black;
    border-left: 3px solid black;
    background-color: white;

    font-weight: 300;
  }

  .p-title {
    font-size: 72px;
    line-height: 84px;
    padding-top: 50px;
    color: black;
  }

  .p-subtitle {
    font-size: 32px;
    color: black;
  }

  .blog-container {
    width: 80%;
    margin: 0 auto;
  }

  .blog-title {
    font-size: 60px;
    color: white;
  }

  .blog-container_frontend {
    display: flex;
    align-items: center;
    justify-content: space-around;
    width: 100%;

    border-right: 3px solid white;
    border-bottom: 3px solid white;
  }

  .blog-container_backend {
    display: flex;
    align-items: center;
    justify-content: space-around;
    width: 100%;

    border-left: 3px solid white;
    border-bottom: 3px solid white;
  }

  .blog-icon {
    width: 20%;

    min-width: 200px;
    min-height: 200px;
  }

  .navigate-icon {
    width: 5%;

    min-width: 50px;
    min-height: 80px;
  }
</style>
