<template>
  <div id="app">

      <InputItem @sendInput="resultInput"/><br>
      <ClearAll @sendClear="clear"/><br>
      <ItemList @sendItem="resultItem" :items="items"/>

  </div>
</template>

<script>
import InputItem from './components/InputItem.vue'
import ClearAll from './components/ClearAll.vue'
import ItemList from './components/ItemList.vue'


export default {
  name: 'App',
  components: {
    ItemList,
    ClearAll,
    InputItem
  },
  data() {
    return {
      'items': [],
      'inputValue': null,
    }
  },

  mounted(){
    let itemsToLoad = localStorage.getItem("items");
    this.items = JSON.parse(itemsToLoad);
  },

  watch: {
    items: function(){
      localStorage.setItem("items",JSON.stringify(this.items));
    }
  },

  computed: {
    result(){
      return this.inputValue;
    }
  },

  methods: {
    resultItem(data){
      this.selectKey = data.key;
      this.rate = data.value;
    },
    resultInput(data){
      this.items.push(data);
    },

    clear(){
      this.items = [];
      console.log(this.items);
    },
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
  margin-top: 60px;
}
</style>
