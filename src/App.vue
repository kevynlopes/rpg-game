<template>
  <div id="app" @keydown="moveCharacter">
    <Map :map="map" :characterPosition="characterPosition" />
    <Character
      :name="characterName"
      :hp="characterHp"
      :position="characterPosition"
      @move="moveCharacter"
    />
  </div>
</template>

<script>
import Character from "./components/Character.vue";
import Map from "./components/Map.vue";

export default {
  components: {
    Character,
    Map,
  },
  data() {
    return {
      characterName: "Hero",
      characterHp: 100,
      characterPosition: { row: 0, col: 0 },
      map: [
        ["*", "*", "*", "*"],
        ["*", ".", ".", "*"],
        ["*", ".", ".", "*"],
        ["*", "*", "*", "*"],
      ],
    };
  },
  methods: {
    moveCharacter(direction) {
      const newRow = this.characterPosition.row + direction.row;
      const newCol = this.characterPosition.col + direction.col;

      if (
        newRow >= 0 &&
        newRow < this.map.length &&
        newCol >= 0 &&
        newCol < this.map[0].length &&
        this.map[newRow][newCol] !== "*"
      ) {
        this.characterPosition.row = newRow;
        this.characterPosition.col = newCol;
      }
    },
  },
};
</script>

<style>
/* styles here */
</style>
