<template>
  <div class="bg-black" style="text-align: center; color: white;">
    <h1 class="text-3xl" style="line-height: 84px;">
      Portfolio
    </h1>
    <div class="my-20 text-2xl" style="display: flex; justify-content: space-between; align-items: start; width: 80%; margin: 0 auto;">
      <div v-for="(content, index) in contents" style="text-align: left;">
        <h2 style="border-bottom: 2px solid white; padding-bottom: 5px;">{{ content.title }}</h2>
        <ul class="mb-6" style="padding: 1rem 0;">
          <li v-for="(cc, index) in content.contents">
            {{ cc }}
          </li>
        </ul>
      </div>
    </div>
    <footer class="text-xl" style="border-top: 2px solid white; padding: 1rem 0; ">
      copyright@2020
    </footer>
  </div>
</template>

<script>
    export default {
      data() {
        return {
          contents: []
        }
      },
      async mounted() {
        const fetchData = await require('~/assets/json/footer.json')
        this.contents = fetchData.contents
      }
    }
</script>

<style scoped>

</style>
