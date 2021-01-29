<template>
  <li>
    <base-card>
      <header>
        <h3>{{ resource.title }}</h3>
        <base-button mode="flat" @click="deleteResource(resource.id)">Delete</base-button>
      </header>
      <p>{{ resource.description }}</p>
      <nav>
        <a :href="resource.link">Go to resource web page</a>
      </nav>
    </base-card>
  </li>
</template>

<script>

export default {
  name: "LearningResource",
  inject: ['deleteResource'],
  props: ['resource']
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-content: center;
}

h3 {
  margin: 5px 0;
}

p {
  margin: 5px 0;
}

a {
  text-decoration: none;
  color: crimson;
}

a:hover,
a:active {
  color: #872236;
}

</style>
