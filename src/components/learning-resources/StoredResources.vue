<template>
  <ul>
    <learning-resource v-for="resource in resources" :key="resource.id" :resource="resource"></learning-resource>
  </ul>
  <base-card v-if="resources.length <= 0">
    <p>No resources added</p>
  </base-card>
</template>

<script>
import LearningResource from "@/components/learning-resources/LearningResource";

export default {
  name: "StoredResources",
  components: {LearningResource},
  inject: ['resources']
}
</script>

<style scoped>
ul {
  list-style: none;
  padding: 0;
  margin: auto;
  max-width: 500px;
}

</style>
