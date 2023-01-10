<template>
  <body class="bodyMain">
    <div class="container-fluid h-100">
      <div class="row">
        <div class="h-50 progressBar">
          <div id="bar" class="innerbar"></div>
          <div>
            <b-button v-if="loginState === true">join</b-button>
          </div>
        </div>
      </div>
    </div>
  </body>
</template>
<script>
export default {
  name: "main",
  data() {
    return {
      progressbarHandler: null,
      timeBegan: null,
      MAX_TIME: 4000,
      loginState: false,
    };
  },
  created() {},
  mounted() {
    this.start();
  },
  methods: {
    start() {
      this.timeBegan = new Date();
      let el = document.getElementById("bar");
      el.style.width = "0%";

      if (this.progressbarHandler == null) {
        this.progressbarHandler = setInterval(this.updateProgressbar, 30);
      }
    },
    updateProgressbar() {
      let currentTime = new Date();
      let time = currentTime - this.timeBegan;
      let el = document.getElementById("bar");
      let width = (time / this.MAX_TIME) * 100 + "%";
      width = parseFloat(width).toFixed(2);
      if (width > 100) {
        width = 100;
        this.loginState = true;
      }

      //console.log("width" + width);
      let widthStr = width + "%";
      el.style.width = widthStr;
    },
  },
};
</script>

<!-- Use preprocessors via the lang attribute! e.g. <style lang="scss"> -->
<style>
.innerbar {
  max-width: 330px;
  height: 100%;
  text-align: right;
  height: 8px; /* same as #progressBar height if we want text middle aligned */
  border-radius: 3px;
  background: linear-gradient(#5be6ba, #5ed1ad);
}
.bodyMain {
  background-color: #a4c3ff;
  height: 100%;
}
</style>
