<template>
  <div id="app">
    <VerticalBarChart :values="values1" />
    <VerticalBarChart
      :values="values2"
      :width="width2"
      :scale="scale2"
    />
    <VerticalBarChart/>
  </div>
</template>

<script>
import VerticalBarChart from "./components/VerticalBarChart.vue";

export default {
  name: "App",
  data() {
    return {
      values1: [50, 100, 150, 70, 55],
      values2: [750, 800, 950, 900, 10000],
      scale2: 2,
      width2: 30,
    };
  },
  components: {
    VerticalBarChart,
  },
};
</script>

<style>
</style>
