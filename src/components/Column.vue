<template>
  <div class="column">
    <div class="column-top">
      <Dropdown
      :list="['config', 'patch']"
      :default="0"
      />
      <button class="subtract-button" @click="this.$parent.removeColumn(index);">-</button>
    </div>
    <div class="column-content">
      {{ content }} {{ index }}
    </div>
  </div>
</template>

<script>
import Dropdown from "./Dropdown.vue"
export default {
  components: {
    Dropdown
  },
  props: [
    "content",
    "index"
  ]
}
</script>

<style lang="scss" scoped>
@import "../main.scss";
.column {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  min-width: fit-content;
  border-radius: $size-round-large;
  overflow: hidden;
  border: 2px solid $color-background;
  background-color: $color-menu;

  .column-top,
  .column-content {
    padding: 8px;
  }

  .column-top {
    border-bottom: 2px solid $color-background;
  }

  .column-content {
    flex: 1 1 auto;
  }
}

.subtract-button {
  height: 25px;
  width: 25px;
  float: right;
}
</style>
