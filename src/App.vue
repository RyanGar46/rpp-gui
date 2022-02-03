<template>
  <div class="column-container">
    <column/>
    <column/>
  </div>
</template>

<script>
import Column from './components/column.vue'
export default {
  name: "App",
  components: {
    Column
  }
}
</script>

<style lang="scss">
#app {
  position: absolute;
  height: 100%;
  width: 100%;
  font-family: Helvetica, Arial, sans-serif;
}

.column-container {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: row;
}
</style>
