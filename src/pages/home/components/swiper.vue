<template>
  <div class="wrapper">
  <swiper :options="swiperOption" v-if="showSwiper">
    <!-- slides -->
    <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name:'HomeSwiper',
  data () {
      return {
          swiperOption:{
              pagination:'.swiper-pagination',
              loop:true
          },
      }
  },
  props:{
      list:Array
  },
  computed:{
      showSwiper (){
          return this.list.length
      }
  }
}
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active   //样式穿透
        background :#fff!important
    .wrapper
        // height :31.25vw
        height :0
        width :100%
        overflow :hidden
        padding-bottom :31.25%

        .swiper-img
            width :100%
</style>

