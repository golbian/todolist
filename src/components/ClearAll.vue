<template>
  <div>
      <button v-on:click="clearAll">Clear All</button>
</div>
</template>

<script>

export default {
  name: 'clearAll',

  methods: {
    clearAll(){
      this.$emit('sendClear');
    }
  }
}

</script>
