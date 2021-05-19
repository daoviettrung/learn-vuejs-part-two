<template>
  <header>
    <h1>{{ titleHeader }}</h1>
    <button v-on:click="changeTitle">Thay doi titl header</button>
  </header>
</template>
<script>
export default {
  name: "com-header",
  props: {
    titleHeader: String,
  },
  data() {
    return {
      text: "This is header",
    };
  },
  methods: {
    changeTitle(e) {
        var data = {
            title : 'thay doi header ne ^-^'
        }
        this.$emit('changeTitleEven', data);
    },
  },
};
</script>
<style>
</style>
