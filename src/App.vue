<template>
  <div :style="backgroundStyle" id="app">
    <clock></clock>
  </div>
</template>

<script>
import clock from "./components/ClockComp.vue";
export default {
  name: "App",
  components: {
    clock,
  },
  data() {
    return {
      backgroundStyle: {
        background:
          "conic-gradient(from 90deg at 25% -10%, #ff4500, #d3f340, #7bee85, #afeeee, #7bee85)",
        display: "flex",
        "justify-content": "center",
        "align-items": "center",
        height: "100vh",
        margin: "auto",
      },
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poiret+One&display=swap');

html,
body {
  margin: 0px !important;
  padding: 0px !important;
  height: 100%;
}
</style>