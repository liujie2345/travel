<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市景点
        </div>
        <router-link to='/city'>
        <div class="header-right">
            <span class="iconfont arrow-icon">&#xe737;</span>
            {{this.city}}
        </div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props:{
      city:String
  }
}
</script>

<style lang="stylus" scoped>
    @import '~style/varibles.styl'
    .header
        display: flex
        height: .86rem
        background: $bgcolor
        line-height: .86rem
        color: #fff
    
    .header-left
        width: .64rem
        float: left
        .back-icon
            text-align:center
            font-size: .4rem
    
    .header-right
        width: 1.24rem
        float: right
        text-align: center
        color:white
        .arrow-icon
            font-size: .24rem
            margin-left: -.04rem 
    
    .header-input
        flex: 1
        background: #ffffff
        border-radius: .1rem
        height: .64rem
        line-height: .64rem
        margin-top: .12rem
        margin-left: .2rem
        color: #ccc
        padding-left:.2rem  
</style>
