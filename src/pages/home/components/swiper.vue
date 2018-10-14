<template>
  <div class="wrapper">
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="item of swiperList" :key="item.id">
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
          swiperList: [{
              id:'0001',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1809/86/deb33800de224c02.jpg_750x200_74fb795e.jpg'
          },{
              id:'0002',
              imgUrl:"http://img1.qunarzz.com/piao/fusion/1809/ff/1bf7d3a4f6591002.jpg_750x200_40809f2a.jpg"
          }]
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

