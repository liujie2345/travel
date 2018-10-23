<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_600x330_5597540f.jpg" alt="">
            <div class="banner-info">
                <div class="banner-title">银杏湖乐园</div>
                <div class="banner-number">39</div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGalleryClose"></common-gallary>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
    name:'DetailBanner',
    components:{
        CommonGallary
    },
    data (){
        return {
            showGallary:false,
            imgs:['http://img1.qunarzz.com/sight/p0/1508/f7/f7c3be996152011c.img.jpg_r_800x800_50c4f278.jpg'
                ,'http://img1.qunarzz.com/sight/p0/1508/64/642f83bc418217bf.img.jpg_r_800x800_52e82e5b.jpg']
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
