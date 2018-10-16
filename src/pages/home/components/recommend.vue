<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item">
                <img class="item-img" :src="item.imgUrl" alt="">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-btn">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name:"HomeRecomend",
    data() {
        return{
            recommendList:[{
                id:"001",
                imgUrl:"http://img1.qunarzz.com/sight/p0/1505/f4/f455d92ba582f608.water.jpg_200x200_375e5775.jpg",
                title:"大连圣亚海洋世界",
                desc:"浪漫大连首战，浪漫的海洋主题乐园"
            },{
                id:"002",
                imgUrl:"http://img1.qunarzz.com/sight/p0/1505/f4/f455d92ba582f608.water.jpg_200x200_375e5775.jpg",
                title:"大连圣亚海洋世界",
                desc:"浪漫大连首战，浪漫的海洋主题乐园"
            },{
                id:"003",
                imgUrl:"http://img1.qunarzz.com/sight/p0/1505/f4/f455d92ba582f608.water.jpg_200x200_375e5775.jpg",
                title:"大连圣亚海洋世界",
                desc:"浪漫大连首战，浪漫的海洋主题乐园"
            },{
                id:"004",
                imgUrl:"http://img1.qunarzz.com/sight/p0/1505/f4/f455d92ba582f608.water.jpg_200x200_375e5775.jpg",
                title:"大连圣亚海洋世界",
                desc:"浪漫大连首战，浪漫的海洋主题乐园"
            },]
        } 
    }    
}
</script>

<style lang="stylus" scoped>
    @import '~style/mixins.styl';
    .recommend-title
        line-height :.8rem
        background :#eee
        text-indent :.2rem
        margin-top .2rem
    .item
        display :flex
        height :1.9rem
        overflow :hidden
        .item-img
            width :1.7rem
            height :1.7rem
        .item-info
            flex :1
            padding :.1rem
            min-width :0rem
            .item-title
                line-height :.54rem
                font-size :.32rem
                ellipsis()
            .item-desc
                line-height :.4rem
                color:#ccc
               ellipsis()
            .item-btn
                line-height :.44rem
                margin-top :.16rem
                background :#ff9300
                padding :0 .2rem
                border-radious :.06rem
</style>
