<template>
  <button :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: ['mode']
}
</script>
<style scoped>
button {
  padding: 5px 15px;
  font-family: inherit;
  background-color: crimson;
  border: 1px solid crimson;
  color: white;
  cursor: pointer;
  font-size: 16px;
  outline: none;
}

button:hover,
button:active {
  background-color: #872236;
  border-color: #872236;
}

.flat {
  background-color: transparent;
  color: #dc97a5;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #f5d2d9;
}
</style>
