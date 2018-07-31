<template>
  <div>
    <p>This is MinePage</p>
    <div id = "mine-list" v-for = "data in datas">
      <div v-bind:id="data.money"
      >{{data.money}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Mile",
  data() {
    return {
      // datas: [{ money: 100 }, { money: 1000 }, { money: 10000 }]
      props: ['datas']
    };
  }
};
</script>