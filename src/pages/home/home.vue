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
import {mapState} from 'vuex'
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
      lastCity:"",
      swiperList:[],
      iconList:[],
      recommendList:[],
      weekendList:[]
    }
  },
  computed:{
    ...mapState(['city'])
  },
  methods:{
    getHomeInfo (){
      axios.get('/api/index.json?city=' + this.city).then(this.getHomeInfoSucc)
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
    this.lastCity=city
    this.getHomeInfo()
  },
  activated () {
    if(this.lastCity!==this.city){
      this.lastCity=this.city
      this.getHomeInfo()
    }
  }
}
</script>
<style>

</style>
