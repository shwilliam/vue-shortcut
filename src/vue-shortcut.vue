<template>
  <div class="vue-shortcut">
    <slot></slot>
  </div>
</template>

<script>
import "./shortcut.min.js";

const shortcuts = [
  {
    eventName: "shortcutNextItem",
    emittedLabel: "nextItem"
  },
  {
    eventName: "shortcutPrevItem",
    emittedLabel: "prevItem"
  },
  {
    eventName: "shortcutNewItem",
    emittedLabel: "newItem"
  },
  {
    eventName: "shortcutOpenItem",
    emittedLabel: "openItem"
  },
  {
    eventName: "shortcutSearchItems",
    emittedLabel: "searchItems"
  },
  {
    eventName: "shortcutLoadItems",
    emittedLabel: "loadItems"
  },
  {
    eventName: "shortcutShowHelp",
    emittedLabel: "showHelp"
  }
];

export default {
  name: "VueShortcut",
  created() {
    const listeners = Object.keys(this.$listeners);
    this.usedShortcuts = shortcuts.filter(shortcut =>
      listeners.includes(shortcut.emittedLabel)
    );
    this.usedShortcuts.forEach(
      shortcut =>
        (this[shortcut.emittedLabel] = function() {
          this.$emit(shortcut.emittedLabel);
        }.bind(this))
    );

    this.usedShortcuts.forEach(shortcut =>
      document.addEventListener(shortcut.eventName, this[shortcut.emittedLabel])
    );
  },
  destroyed() {
    this.usedShortcuts.forEach(shortcut =>
      document.removeEventListener(
        shortcut.eventName,
        this[shortcut.emittedLabel]
      )
    );
  }
};
</script>

<style scoped>
</style>
