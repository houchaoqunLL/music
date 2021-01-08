<template>
  <div id="app">
    <!-- 相当于直接放标签样式上去: -->
    <TopNav></TopNav>
    <!-- 是路由匹配视图组件显示的位置 -->
    <router-view/>
  </div>
</template>
<script>
import TopNav from "./components/TopNav"
export default {
  components:{
    TopNav
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
