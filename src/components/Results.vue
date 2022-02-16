<template>
  <div>
    <p>Reaction Time is: {{ result }} ms</p>
    <h1>{{ rank }}</h1>
  </div>
</template>

<script>
export default {
  props: ["result"], //get from Parent
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.result < 250) {
      this.rank = "OMG! You are FAST!";
    } else if (this.result < 400) {
      this.rank = "Not bad :>";
    } else {
      this.rank = "How old are you? 70?";
    }
  },
};
</script>

<style>
</style>