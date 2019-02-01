<template>
  <div class="slides">
    <div class="slide" :style="{ backgroundColor: getBgColor(currentSlideIndex) }">
      <p class="slide-number">Slide: {{ currentSlideIndex + 1 }}</p>
      <p class="instructions">Press the 'J' and 'K' keys to navigate the slides</p>
    </div>
  </div>
</template>

<script>
const bgColors = ["yellow", "blue", "red", "green", "pink", "purple"];

export default {
  name: "Slides",
  props: ["currentSlideIndex"],
  methods: {
    getBgColor(i) {
      return bgColors[i];
    }
  }
};
</script>

<style scoped>
.slide {
  width: 100%;
  height: 100vh;
}
.instructions {
  margin: 0 auto;
  width: 100%;
  height: 100%;
  display: grid;
  text-align: center;
  align-content: center;
}
</style>