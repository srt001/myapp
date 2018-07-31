<template>
  <div id="bottomNav">
    <router-link to="/" class="tab">首页</router-link>
    <router-link to="/mine" class="tab">我的</router-link>
  </div>
</template>

<script>
  export default {
    name : "bottomNav",
    data() {
      return {

      }
    },
    //从父组件传值到子组件
    props: ['logo']
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #bottomNav {
    display: flex;
    width: 100%;
    height: 3rem;
    line-height: 3rem;
    padding: 0.5rem 0;
    text-align: center;
    border-top: 1px solid #999999;
    position: fixed;
    left: 0;
    bottom: 0;
    background-color: aliceblue;
  }

  .tab {
    flex: 1;
    text-align: center;
    border-right: 1px solid #999999;
  }
</style>