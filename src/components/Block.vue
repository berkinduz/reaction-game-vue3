<template>
  <div class="block" v-show="showBlock" @click="stopTimer">Click Me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay); // show block depends on delay props value
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10); // increase reacTion time every 10ms until stopTimer called
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("end", this.reactionTime); //parent calls it with parameter
    },
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>