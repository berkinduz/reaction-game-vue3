<template>
  <p>Reaction Time is: {{ result }} ms</p>
</template>

<script>
export default {
  props: ["result"], //get from Parent
};
</script>

<style>
</style>