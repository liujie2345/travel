<template>
  <div class="icons">
      <swiper>
        <swiper-slide v-for="(page,index) of pages" :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
                <div class="icon-img">
                    <img class="icon-img-content" :src="item.imgUrl" alt="">
                </div>
                <p class="icon-desc">{{item.desc}}</p>
            </div>
        </swiper-slide>
      </swiper>
  </div>
</template>

<script>
export default {
  name:'HomeIcons',
  data() {
      return {
          iconList: [{
              id:'0001',
              imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
              desc:'景点门票'
          },{
              id:'002',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
              desc:'滑雪季'
          },{
              id:'003',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
              desc:'动物园'
          },{
              id:'004',
              imgUrl:'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
              desc:'泡温泉'
          },{
              id:'005',
              imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png",
              desc:'中山陵'
          },{
              id:'006',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
              desc:'总统府'
          },{
              id:'007',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
              desc:'一日游'
          },{
              id:'008',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
              desc:'文化古迹'
          },{
              id:'009',
              imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
              desc:'文化古迹'
          }]
      }
  },
  computed: {
      pages() {
          const pages = [];
          this.iconList.forEach((item,index) => {
              const page = Math.floor(index/8)
              if (!pages[page]) {
                  pages[page] = []
              }
              pages[page].push(item)
          })
        return pages
      }
  }
}
</script>

<style lang="stylus" scoped>
    @import '~style/varibles.styl';
    @import '~style/mixins.styl';
    .icons >>> .swiper-container
        height :0
        padding-bottom :50%
        .icon
            position: relative
            overflow: hidden
            float: left
            width: 25%
            height :0
            padding-bottom: 25%
        
        .icon-img
            position: absolute
            top: 0
            left: 0
            right: 0
            bottom: .44rem
            box-sizing:border-box
            padding :.1rem
            .icon-img-content
                display :block
                margin :0 auto
                height :100%
        
        .icon-desc 
            position: absolute
            left :0
            right :0
            bottom :0
            height :.44rem
            line-height :.44rem
            color :$darkTextColor
            text-align :center
            ellipsis()

</style>
