<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h2>Monster</h2>
    <p>HP: {{ hp }}</p>
    <button @click="attack">Attack</button>
  </div>
</template>

<script>
export default {
  props: {
    hp: Number,
    attackPower: Number,
  },
  methods: {
    attack() {
      this.$emit("attack", this.attackPower);
    },
  },
};
</script>
