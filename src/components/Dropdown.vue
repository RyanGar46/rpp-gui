<template>
  <div class="dropdown-container">
    <div class="dropdown">{{ selected }}</div>
    <div class="dropdown-items">
      <button
      v-for="item in list"
      :key="item"
      @click="selectItem(item);"
      >
      {{ item }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    list: {
      type: Array
    },
    default: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      items: [],
      selected: this.list[this.default]
    }
  },
  methods: {
    selectItem(item) {
      this.selected = item
    }
  }
}
</script>

<style lang="scss" scoped>
@import "../main.scss";
.dropdown-container {
  width: fit-content;
  user-select: none;

  .dropdown {
    background-color: $color-background;
    padding: $size-padding-small;
    border-radius: $size-round-normal;
    border: 2px solid transparent;
  }
  .dropdown:hover {
    border-color: $color-accent;
  }

  .dropdown-items {
    opacity: 0;
    visibility: none;
    display: flex;
    flex-direction: column;
    position: fixed;
    margin-top: $size-margin-normal;
    width: fit-content;
    overflow: hidden;
    border-radius: $size-round-normal;
    background-color: $color-background;

    * {
      padding: $size-padding-small;
      border-radius: $size-round-normal;
      border: none;
      font-size: $size-font-normal;
      text-align: left;
      background-color: $color-background;
      color: $color-text;
    }
    *:hover {
      background-color: $color-accent;
    }
  }
}

.dropdown-container:hover .dropdown-items,
.dropdown-items:hover {
  opacity: 1;
  visibility: initial;
}
</style>
