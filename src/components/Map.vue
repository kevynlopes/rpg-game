<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="map">
    <div v-for="(row, rowIndex) in map" :key="rowIndex" class="map-row">
      <div
        v-for="(cell, cellIndex) in row"
        :key="cellIndex"
        class="map-cell"
        :class="{
          active:
            rowIndex === characterPosition.row &&
            cellIndex === characterPosition.col,
        }"
      >
        {{ cell }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["map", "characterPosition"],
};
</script>

<style scoped>
.map {
  display: flex;
  flex-direction: column;
}

.map-row {
  display: flex;
}

.map-cell {
  width: 30px;
  height: 30px;
  border: 1px solid black;
}

.active {
  background-color: blue;
}
</style>
