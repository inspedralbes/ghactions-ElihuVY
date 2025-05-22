<template>
  <div class="calculator">
    <button
      v-for="number in numbers"
      :key="number"
      @click="showNumber(number)"
    >
      {{ number }}
    </button>
    <p v-if="selected">Has clicado el número: {{ selected }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9],
      selected: null,
    };
  },
  methods: {
    showNumber(n) {
      this.selected = n;
    },
  },
};
</script>

<style>
.calculator {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  width: 200px;
  margin: 20px auto;
}
button {
  padding: 20px;
  font-size: 1.5rem;
}
</style>
