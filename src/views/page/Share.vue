<template>
<div class="home">         
                   <div class="item"  v-for="(item,index) in dataList" :key="index">
                    <div class="media">
                           <img width="300px" height="200px" :src="item.url" alt="" />
                       </div>
                       <div class="content" @click="goPage(item)">
                           <div class="title" v-text="item.title"></div>
                           <div class="sub-title" v-text="item.subTitle"> 至今最开心的夏天，愿能再次相遇</div> 
                          <div class="attr" v-text="item.attr"> 2018-08-16</div>
                       </div>    
                   </div>
</div>
</template>
<script type="text/babel">
export default {
    data(){
        return {
            dataList:[
                {
                    title:"从《搜索》中探究什么是道德",
                    subTitle:"序、道德和犯罪、道德下的权力失控、什么是道德、教科书里的道德、道德标杆只是时代的产物、大逃杀下的道德崩溃、道德只是丛林法则的分支、道德的前提是公平公正",
                    attr:"2018-9-07",
                    url:"/img/9.jpg",
                    content:'会越来越好'
                }
            ]
        }
    },
    methods:{
        getUrl(url){
            return '@/assets/'+url;
        },
        goPage(item){
            this.$router.push('/Medetail')
            localStorage.setItem('detail',JSON.stringify(item));
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" rel="stylesheet/stylus" scoped>
.home
    width 100%
    height auto 
    padding 20px 12px
    background #f0f0f0
    .item
        padding 5px
        display flex
        flex-direction row
        overflow hidden
        height 240px
        width 100%
        margin-left 200px
        .content 
            line-height 50px
            cursor pointer
            margin-left 20px
            .title
                line-height 70px
                font-size 32px
                font-weight 600
                color #0f0f0f
                font-family SimSun
            .sub-title
                line-height 40px
                font-weight 200
                font-size 20px
                color #444444
            .attr
                line-height 50px
                font-weight 100
                font-size 16px
                color #444444
        img
           border-radius 4px
</style>
