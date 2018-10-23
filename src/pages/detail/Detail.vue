<template>
    <div>
        <detail-banner></detail-banner>
        <detail-header></detail-header>
        <detail-list :list="List"></detail-list>
    </div>
</template>

<script>
import DetailBanner from './components/banner'
import DetailHeader from './components/Header'
import DetailList from './components/list'
export default {
    name:'Detail',
    components:{
        DetailBanner,
        DetailHeader,
        DetailList
    },
    data () {
        return {
            List:[{
                title:"成人票",
                children:[{
                    title:'成人三馆联票',
                    children:[{
                        title:'成人三观联票 - 某一连锁店销售'
                    }]
                },{
                    title:'成人五馆联票'
                }]
                    
            },{
                title:"学生票"
            },{
                title:"儿童票"
            },{
                title:"特惠票"
            }]
        }
    }
}
</script>

<style lang="stylus" scoped>

</style>
