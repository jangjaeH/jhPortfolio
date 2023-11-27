<template>
  <body class="bodyMain">
    <div
      class="container-fluid w-100 h-100 d-flex justify-content-center align-items-center"
    >
      <div v-if="joinState === false">
        <div class="h-50 progressBar">
          <div id="bar" class="innerbar"></div>
        </div>
      </div>
      <div
        v-if="joinState === true"
        class="border rounded border-dark content-items d-flex justify-content-center align-items-center bg-white"
      ></div>
    </div>
    <profile />
  </body>
</template>
<script>
import profile from "./profile";
export default {
  name: "main",
  components: {
    profile,
  },
  data() {
    return {
      progressbarHandler: null,
      timeBegan: null,
      MAX_TIME: 2500,
      loginState: false,
      joinState: false,
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
      if (this.joinState === false) {
        el.style.width = widthStr;
      }
    },
    onprofile() {
      this.$bvModal.show("propfileModal");
    },
    onHome() {
      window.open("https://google.com");
    },
    onInstar() {
      window.open("https://www.instagram.com/dev_jhjang___._.j");
    },
    onGithub() {
      window.open("https://github.com/jangjaeH");
    },
    onFacebook() {
      window.open("https://www.facebook.com/profile.php?id=100008292990107");
    },
  },
};
</script>

<!-- Use preprocessors via the lang attribute! e.g. <style lang="scss"> -->
<style>
.innerbar {
  max-width: 600px;
  height: 20px; /* same as #progressBar height if we want text middle aligned */
  border-radius: 3px;
  background: linear-gradient(#5be6ba, #5ed1ad);
}
.bodyMain {
  background-color: #6667ab;
  height: 100%;
}
.container-table {
  display: table;
}
.vertical-center-row {
  display: table-cell;
  vertical-align: middle;
}
.progressBar {
  width: 400px;
}
.content-items {
  width: 500px;
  height: 300px;
}
.items {
  width: 100px;
  height: 100px;
  margin-right: 5px;
}
</style>
