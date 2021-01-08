<template>
  <div class="recommend">
    <Title>推荐歌单</Title>
    <ul class="remcommendList">
      <router-link v-for="rem in recommendMusic" :key="rem.id" to='/' tag="li">
      <div>
        <img :src="rem.picUrl" alt="">
        <span>{{rem.playCount | formatNum}}</span>
      </div>
        <p>{{rem.name}}</p>
      </router-link>
    
    </ul>
    <Title>最新音乐</Title>
    
    <Musictem :newMusiclist="newMusicList"></Musictem>
    
  </div>
</template>

<script>
// @ is an alias to /src

import Title from '../components/Title.vue'
import Musictem from "../components/Musictem"
export default {
  
  components: {
    Title,
    Musictem
  },
  data(){
    return{
      recommendMusic:[],
      newMusicList:[]
    }
  },
  beforeRouteEnter(to,from,next){//路由守卫,进入之前获取数据
  next(vm=>{
    vm.$http.get('/personalized?limit=6').then(data=>{
    vm.recommendMusic=data.data.result;
    
  });
    vm.$http.get('/personalized/newsong').then(data=>{
    vm.newMusicList=data.data.result;
    // console.log(data.data.result);
  });
  });
  },
  filters:{
    formatNum(value){
      return(value/10000).toFixed(1)+"万"
    }
    
  }
  
}
</script>

<style lang="less">
  ul.remcommendList{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 24px;
    li{
      width: 33%;
      margin-bottom: 16px;
      div{
        position: relative;
        span{
          position: absolute;
          top: 2px;
          right: 3px;
          color: white;
          text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
        }
      }
      p{
        display: -webkit-box;
        text-align: left;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
        padding: 6px 2px 0 6px;
        min-height: 30px;
        line-height: 1.2;
        font-size: 13px;
      }
    }
  }
</style>
