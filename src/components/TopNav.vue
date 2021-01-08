<template>
    <div class="box">
        <div class="top">
            <div class="top1"></div>
            <div class="top2">下载APP</div>
        </div>
    <ul class="topnav">
        <li><router-link tag="a" to="/">推荐音乐</router-link></li>
        <li><router-link tag="a" to="/hot">热歌榜</router-link></li>
        <li><router-link tag="a" to="/search">搜索</router-link></li>
    </ul>
    </div>
</template>

<script>
export default {
    
}
</script>

<style lang="less">
.top{
    width: 100%;
    height: 84px;
    background-color: #e60026;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .top1{
        width: 140px;
        height: 44px;
        background: url(../assets/title1.png) no-repeat 6px -6px/200px auto;
    }
    .top2{
        width: 100px;
        height: 36px;
        background-color: white;
        color: #d43c33;
        font-size: 20px;
        border-radius: 20px;
        line-height: 36px;
        margin-right: 15px;
    }
}
.topnav{
    display: flex;
    border-bottom: 1px solid #ddd;
    
    li{
        
        flex: 1 1 auto;
        font-size: 15px;
        a{
            display: inline-block;
            text-decoration: none;
            color: black;
            height: 40px;
            line-height: 40px;
            &.router-link-exact-active{
                color: red;
                border-bottom: 2px solid red;
            }

        }
    }
}
</style>