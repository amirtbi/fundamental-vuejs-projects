<template>
  <div class="resource-container" :class="type">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: ["type"],
};
</script>
<style scoped>
div.resource-container {
  display: flex;

  box-shadow: 0 2px 10px #ccc;
  border-radius: 2px;
}
.rowContainer {
  flex-direction: row;
  width: 500PX;
  justify-content: center;
  align-items: center;
  padding: 1.5rem;
  margin:0 auto;
}
.columnContainer {
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  width: 500px;
  margin:auto;
}
</style>
