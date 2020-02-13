<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.key">{{item}}<button v-on:click="suppr"> X </button></li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'ItemList',
  props: {
    items: Array,
  },

  methods: {
    suppr:function(e){
      let itemToDelete = this.items.indexOf(e.target.parentNode.firstChild.data);
      this.items.splice(itemToDelete,1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
