<template>
  <div class="barchart-container">
    <div
      v-for="(value, i) of values"
      class="barchart-container__bar"
      v-bind:key="i"
      :style="barStyle(value)"
    ></div>
  </div>
</template>

<script>
export default {
  /**
   * Vertical bar chart
    */
  props: {
    /**
     * 
     */
    values: {
      type: Array,
    },
    width: {
      type: Number,
      default: 25,
    },
    scale: {
      type: Number,
      default: 1,
    },
  },
  methods: {
    barStyle(value) {
      return `
        height: ${value*this.scale}px;
        width: ${this.width}px
      `;
    },
  },
};
</script>

<style scoped>
.barchart-container {
  display: flex;
  align-items: flex-end;
  margin: 5px;
}
.barchart-container__bar {
  margin: 0px 5px;
  background-color: rgb(47, 118, 180);
}
</style>