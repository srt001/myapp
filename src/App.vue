<template>
  <div id="app">
    <img class="logo" src="./assets/logo.png">
    <!-- <router-view/> -->
    <!--3，将组件写入页面-->
    <!-- <BottomNav :logo = "logo"></BottomNav> -->
    <Login></Login>
  </div>
</template>

<script>
//1,导入组件
import Login from "./components/Login.vue";
import BottomNav from "./components/BottomNav.vue";
export default {
  name: "app",
  data() {
    return {
      logo: "1112233"
    };
  },
  //2,注册组件
  components: {
    Login,
    BottomNav
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
.logo {
  height: auto;
  width: 100%;
}
</style>
