<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h2>{{ name }}</h2>
    <p>HP: {{ hp }}</p>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    hp: Number,
    position: Object,
  },
  methods: {
    move(direction) {
      this.$emit("move", direction);
    },
  },
};
</script>
