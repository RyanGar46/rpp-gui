<template>
  <div class="column">
    <div class="column-top">
      <input type="text"/>
      <button class="subtract-button" @click="this.$parent.removeColumn(index);">-</button>
    </div>
    <div class="column-content">
      {{ content }} {{ index }}
    </div>
  </div>
</template>

<script>
export default {
  props: [
    "content",
    "index"
  ]
}
</script>

<style lang="scss" scoped>
.column {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  min-width: fit-content;
  border-radius: 8px;
  overflow: hidden;
  border: 2px solid rgb(37, 37, 37);
  background-color: rgb(45, 47, 49);

  .column-top,
  .column-content {
    padding: 8px;
  }

  .column-top {
    border-bottom: 2px solid rgb(37, 37, 37);
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
