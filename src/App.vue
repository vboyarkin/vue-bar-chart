<template>
  <div id="app">
    <VerticalBarChart v-bind:values="values1" />
    <VerticalBarChart
      v-bind:values="values2"
      v-bind:width="width2"
      v-bind:scale="scale2"
    />
  </div>
</template>

<script>
import VerticalBarChart from "./components/VerticalBarChart.vue";

export default {
  name: "App",
  data() {
    return {
      values1: [50, 100, 150, 70, 55],
      values2: [70, 150, 44, 71, 55],
      scale2: 2,
      width2: 6,
    };
  },
  components: {
    VerticalBarChart,
  },
};
</script>

<style>
</style>
