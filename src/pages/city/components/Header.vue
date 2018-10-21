<template>
    <div class="header">
        城市选择
        <router-link to="/">
        <div class="iconfont header-back">&#xe624;</div>
        </router-link>
    </div>    
</template>

<script>
export default {
    
}
</script>

<style lang="stylus" scoped>
 @import '~style/varibles.styl'
    .header
        position :relative
        height :.86rem
        line-height :.86rem
        text-align :center
        color :#fff
        background :$bgcolor
        font-size :.32rem    
    .header-back
        top:0
        left :0
        position :absolute
        width :.64rem
        text-align :center
        font-size :.4rem
        color:#fff  
</style>
