<template>
  <div class="rounded-full flex items-center justify-center h-56 w-56 bg-white">
    <img :src="require(`~/assets/image/top/blog/${image}`)" class='blog-image' alt='no_image'/>
  </div>
</template>

<script>
    export default {
      props :{
        image: {
          type: String,
          required: true
        }
      }
    }
</script>

<style scoped>
  .blog-image {
    width: 70%;
  }
</style>
