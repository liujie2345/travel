<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" :src="this.bannerImg" alt="">
            <div class="banner-info">
                <div class="banner-title">{{this.sightName}}</div>
                <div class="banner-number">{{this.bannerImgs.length}}</div>
            </div>
        </div>
        <fade>
            <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGalleryClose"></common-gallary>
        </fade>
        
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import Fade from 'common/fade/fade'
export default {
    name:'DetailBanner',
    components:{
        CommonGallary,
        Fade
    },
    props:{
        sightName:String,
        bannerImg:String,
        bannerImgs:Array
    },
    data (){
        return {
            showGallary:false
        }
    },
    methods:{
        handleBannerClick () {
            this.showGallary=true
        },
        handleGalleryClose (){
            this.showGallary=false
        }
    }
}
</script>

<style lang="stylus" scoped>
    .banner
        position :relative
        overflow :hidden
        height :0
        padding-bottom :55%
        .banner-img
            width :100%
        .banner-info
            display :flex
            position :absolute
            left:0
            right :0
            bottom :0
            line-height :.6rem
            color:#fff
            // background-image :linear-gradient(top,rgab(0,0,0,0),rgba(0,0,0,0.8))
            background :linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
            .banner-title
                flex :1
                font-size: 0.32rem
                padding :0 .2rem
            .banner-number
                padding :0 .4rem
                line-height :.32rem
                height :.32rem
                border-radius :0.2rem
                background :rgba(0,0,0,.8)
                font-size :.24rem
                margin-top :.14rem
</style>
