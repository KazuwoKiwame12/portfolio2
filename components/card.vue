<template>
  <div class="p-card overflow-hidden shadow-lg">
    <img :src="require(`~/assets/image/top/service/${image}`)" class='card-image' alt='no_image'/>
    <div class="px-6 py-4">
      <div class="font-bold text-3xl mb-2">{{ title }}</div>
      <p class="text-gray-700 text-2xl">
        {{ description }}
      </p>
    </div>
  </div>
</template>

<script>
    export default {
        props :{
          image: {
            type: String,
            required: true
          },
          title: {
            type: String,
            required: true
          },
          description: {
            type: String,
            required: true
          }
        }
    }
</script>

<style scoped>
  .p-card {
    height: 440px;
    background-color: white;
    border-radius: 30px;
    text-align: center;
  }

  .card-image {
    display: inline-block;
    margin-top: 20px;

    width: 50%;
    max-width: 180px;
    height: auto;
  }
</style>
