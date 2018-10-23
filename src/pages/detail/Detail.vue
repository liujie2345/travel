<template>
    <div>
        <detail-banner 
        :sightName="sightName" 
        :bannerImg="bannerImg"
        :bannerImgs="gallaryImgs"
        ></detail-banner>
        <detail-header></detail-header>
        <detail-list :list="List"></detail-list>
    </div>
</template>

<script>
import DetailBanner from './components/banner'
import DetailHeader from './components/Header'
import DetailList from './components/list'
import axios from 'axios'
export default {
    name:'Detail',
    components:{
        DetailBanner,
        DetailHeader,
        DetailList
    },
    data () {
        return {
            sightName:'',
            bannerImg:'',
            gallaryImgs:[],
            List:[]
        }
    },
    mounted (){
        this.getDetailInfo()
    },
    methods:{
        getDetailInfo (){
            axios.get('/api/detail.json?',{
                params:{
                    id:this.$route.params.id
                }
            }).then(this.handleGetDataSucc)
        },
        handleGetDataSucc (res) {
            res=res.data
            if(res.ret && res.data){
                const data=res.data
                this.sightName=data.sightName
                this.bannerImg=data.bannerImg
                this.gallaryImgs=data.gallaryImgs
                this.List=data.categoryList
            }
        }
    }
}
</script>

<style lang="stylus" scoped>

</style>
