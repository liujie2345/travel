<template>
    <ul class="list">
        <li 
        class="item" 
        v-for="item of letters" 
        :key="item"
        :ref="item" 
        @click="handleLetterClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        >{{item}}</li>
    </ul>
</template>

<script>
export default {
    name:"CityAlphabet",
    props:{
        cities:Object
    },
    computed:{
        letters() {
            const letters=[]
            for(let i in this.cities){
                letters.push(i)
            }
            return letters
        }
    },
    methods:{
        handleLetterClick(e){
            this.$emit('change',e.target.innerText);
        },
        handleTouchStart(){
            this.touchStatus=true
        },
        handleTouchMove(e){
            // console.log(this.letters);
            if(this.touchStatus=true){
                if(this.timer){
                    clearTimeout(this.timer)
                }
                this.timer=setTimeout(()=>{
                    const startY=this.startY
                    const touchY=e.touches[0].clientY-79
                    const index=Math.floor((touchY-startY)/20)
                    if(index>=0 && index<this.letters.length){
                        this.$emit('change',this.letters[index])
                    }
                },16) 
            }
        },
        handleTouchEnd(){
            this.touchStatus=false
        }
    },
    data(){
        return {
            touchStatus:false,
            startY:0,
            timer:null
        }
    },
    updated (){
        this.startY=this.$refs['A'][0].offsetTop
    }
}
</script>

<style lang="stylus" scoped>
    @import '~style/varibles.styl';
    .list
        display :flex
        flex-direction :column
        justify-content :center
        position :absolute
        right :0
        top :1.78rem
        bottom :0
        width :.4rem
        .item
            text-align :center
            line-height :.4rem
            color :$bgcolor
</style>
