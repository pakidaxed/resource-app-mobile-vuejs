<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  name: "TheHeader",
  props: ['title']
}
</script>

<style scoped>
header {
  width: 100%;
  height: 80px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: crimson;
}

header h1 {
  color: white;
  margin: 0;
}
</style>
