<template>
  <div class="barchart-container">
    <div
      v-for="value of getIdAndStyle"
      class="barchart-container__bar"
      :key="value.id"
      :style="value.style"
    ></div>
  </div>
</template>

<script>
import { nanoid } from "nanoid";

export default {
  /**
   * Vertical bar chart
   */
  props: {
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
    heightLimit: {
      type: Number,
      default: 400,
    },
  },
  computed: {
    /**
     * Returns array of unique IDs and computed styles for each bar
     */
    getIdAndStyle() {
      if (!this.values || this.values.length === 0) return [];

      const maxHeight = this.scale * Math.max(...this.values);
      const limitingScale =
        maxHeight > this.heightLimit ? this.heightLimit / maxHeight : 1;

      return this.values.map((value) => {
        const height = value * limitingScale;
        const style = `
          height: ${height}px;
          width: ${this.width}px
        `;
        
        return {
          id: nanoid(5),
          style,
        };
      });
    },
  },
};
</script>

<style scoped>
.barchart-container {
  display: flex;
  align-items: flex-end;
  margin: 7px 0px;
}
.barchart-container__bar {
  margin: 0px 5px;
  background-color: rgb(47, 118, 180);
}
</style>