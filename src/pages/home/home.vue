<template>
    <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <weekend :list="weekendList"></weekend>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/swiper'
import HomeIcons  from './components/icons'
import HomeRecommend from './components/recommend'
import Weekend from './components/weekend'
import axios from 'axios' 
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    Weekend
  },
  data (){
    return {
      swiperList:[],
      iconList:[],
      recommendList:[],
      weekendList:[]
    }
  },
  methods:{
    getHomeInfo (){
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res){
      console.log(res);
      res=res.data;
      if(res.ret && res.data){
        this.swiperList=res.data.swiperList
        this.iconList=res.data.iconList
        this.recommendList=res.data.recommendList
        this.weekendList=res.data.weekendList
      }
    }
  },
  mounted() {
    this.getHomeInfo()
  }
}
</script>
<style>

</style>
