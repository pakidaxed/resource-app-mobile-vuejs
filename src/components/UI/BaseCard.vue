<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "BaseCard"
}
</script>

<style scoped>
div {
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
  padding: 10px;
  margin: 15px auto;
  max-width: 500px;
}
</style>
