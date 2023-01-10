<template>
  <footer class="fixed-bottom bg-dark">
    <div class="d-flex justify-content-between">
      <div class="p-2 text-white">@2023 JangJaeHyeoks</div>
      <div class="ml-auto p-2 border border-white text-white rounded">
        {{ nowTime }}
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  name: "footerLayout",
  data() {
    return {
      nowTime: null,
    };
  },
  created() {
    this.nowTimes();
    this.setDate();
    setInterval(this.nowTimes.bind(this), 1000);
  },
  methods: {
    setDate() {
      let hh =
        new Date().getHours() < 10
          ? "0" + new Date().getHours()
          : new Date().getHours();
      let mm =
        new Date().getMinutes() < 10
          ? "0" + new Date().getMinutes()
          : new Date().getMinutes();
      return {
        hh: hh,
        mm: mm,
      };
    },
    nowTimes() {
      this.nowTime = this.setDate().hh + "시" + this.setDate().mm + "분";
    },
  },
};
</script>
