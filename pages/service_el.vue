<template>
  <div class="p-service">
    <h1 class="p-title">Service</h1>
    <h3 class="p-subtitle">introduce about my skills</h3>
    <div class="service-container_top" >
      <div class="card-size my-20" v-for="(card, index) in cardInfos_top">
        <card :image="card.image" :title="card.title" :description="card.description"/>
      </div>
    </div>
    <div class="service-container_bottom" >
      <div class="card-size content-position" v-for="(card, index) in cardInfos_bottom">
        <card :image="card.image" :title="card.title" :description="card.description"/>
      </div>
    </div>
  </div>
</template>

<script>
  import card from '~/components/card'
    export default {
        components: {
          card
        },
      data() {
          return {
            cardInfos_top: [],
            cardInfos_bottom: []
          }
      },
      async mounted() {
        const fetchData = await require('~/assets/json/cardInfos.json')
        this.cardInfos = fetchData.cardInfos
        this.cardInfos_top.push(this.cardInfos[0])
        this.cardInfos_top.push(this.cardInfos[1])
        this.cardInfos_top.push(this.cardInfos[2])
        this.cardInfos_bottom.push(this.cardInfos[3])
        this.cardInfos_bottom.push(this.cardInfos[4])
      }
    }
</script>

<style scoped>
  .p-service {
    text-align: center;
    width: 100%;
  }

  .p-title {
    font-weight: 300;
    font-size: 72px;
    line-height: 84px;
    padding-top: 10px;
    color: white;
  }

  .p-subtitle {
    font-weight: 300;
    font-size: 32px;
    color: white;
  }

  .service-container_top {
    display: flex;
    align-items: center;
    justify-content: space-around;
    width: 100%;

    border-right: solid 3px white;
  }

  .card-size {
    width: 28%;
    max-width: 360px;
  }

  .service-container_bottom {
    display: flex;
    align-items: center;
    justify-content: space-around;
    width: 100%;
    height: 200px;

    border-top: solid 3px white;
    border-right: solid 3px white;
  }

  .content-position {
    position: relative;
    top: 200px;
  }
</style>
