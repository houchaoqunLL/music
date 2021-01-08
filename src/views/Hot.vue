<template>
  <div class="hot">
    <div class="topbig">
        <div class="top2"></div>
        <div class="topp">更新日期:01月07日</div>
    </div>
    <!-- <Musictem :newMusiclist="newMusicList"></Musictem> -->
  </div>
</template>

<script>
// import Musictem from "../components/Musictem"
export default {
    components:{
        // Musictem
    },
    data(){
        return{
            // newMusiclist:[]
        }
    },
    beforeRouteEnter(to,from,next){
        console.log(1);
        next(vm=>{
            vm.$http.get('/top/list?idx=6').then(data=>{
                // vm.newMusiclist=data.data.result;
                console.log(data);
            })
        });
    }
}
</script>

<style lang="less" scoped>
.topbig{
    width: 100%;
    height: 145px;
    padding-top: 20px;
    background: url(../assets/bg1.jpg) no-repeat;
    background-size: contain;
    position: relative;
    .top2{
        margin-left: 15px;
        
        width: 142px;
        height: 67px;
        background: url(../assets/bg2.png) no-repeat;
        background-size: 166px 97px;
        background-position: -24px -30px;
        // position: absolute;
    }
    .topp{
        text-align: left;
        font-size: 12px;
        color: white;
        margin-left: 15px;
        margin-top: 12px;
    }
}
</style>