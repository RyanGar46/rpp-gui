<template>
  <div class="column-container">
    <div class="column-container">
      <Column
      v-for="(content, index) in columns"
      :key="index"
      :content="content"
      :index="index"
      />
    </div>
    <button class="column-button" @click="addColumn();">+</button>
  </div>
</template>

<script>
import Column from "./components/Column.vue";
export default {
  name: "App",
  components: {
    Column
  },
  data() {
    return {
      columns: {},
      index: 0
    }
  },
  methods: {
    addColumn() {
      this.columns["column" + this.index] = { type: "new", file: "", content: "" };
      this.index++;
    },
    removeColumn(i) {
      delete this.columns[i];
    }
  }
}
</script>

<style lang="scss">
@import "./main.scss";
#app {
  position: absolute;
  height: 100%;
  width: 100%;
  color: $color-text;
  background-color: $color-background;
  font-family: Helvetica, Arial, sans-serif;
  font-size: $size-font-normal;
}

.column-container {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: row;
  overflow: auto;
}
</style>
