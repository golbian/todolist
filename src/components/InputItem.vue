<template>
  <div>
  <form @submit.prevent="updateItem">
      <input type="text" v-model="inputValue">
      <input type="submit" name="">
  </form>
</div>
</template>

<script>

export default {
  name: 'InputItem',

  data() {
    return {
      'inputValue': null,
    }
  },

  methods: {
    updateItem(){
      this.$emit('sendInput', this.inputValue);
    }
  }
}

</script>
