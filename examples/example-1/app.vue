<template>
  <div id="app">
    <VueShortcut @nextItem="updateCurrentIndex(1)" @prevItem="updateCurrentIndex(-1)">
      <Slides :currentSlideIndex="currentSlideIndex"/>
    </VueShortcut>
  </div>
</template>

<script>
import VueShortcut from "../../src/vue-shortcut.vue";
import Slides from "./components/slides.vue";

export default {
  name: "App",
  components: {
    VueShortcut,
    Slides
  },
  data() {
    return {
      currentSlideIndex: 0
    };
  },
  methods: {
    updateCurrentIndex(increment) {
      const maxSlidesIndex = 5;
      if (this.currentSlideIndex + increment > maxSlidesIndex) {
        this.currentSlideIndex = 0;
      } else if (this.currentSlideIndex + increment < 0) {
        this.currentSlideIndex = maxSlidesIndex;
      } else {
        this.currentSlideIndex = this.currentSlideIndex + increment;
      }
    }
  }
};
</script>

<style>
/* reset */
html,
body,
p {
  margin: 0;
  padding: 0;
}

/* app */
#app {
  height: 100vh;
  width: 100vw;
  overflow: hidden;
}
</style>
