<template>
  <the-header title="Resources Mobile APP"></the-header>
  <div class="container">
    <the-resources></the-resources>
  </div>
</template>

<script>
import TheHeader from "@/components/layouts/TheHeader";
import TheResources from "@/components/learning-resources/TheResources";

export default {
  name: 'App',
  components: {
    TheResources,
    TheHeader,
  },

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:ital,wght@0,300;0,700;1,300&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Open Sans Condensed', sans-serif;
}

body {
  margin: 0;
}

.container {
  padding: 0 5px;
}
</style>
