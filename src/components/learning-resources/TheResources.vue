<template>
  <base-card>
    <base-button @click="setSelectedTab('stored-resources')" :mode="storedResourcesBtnMode">Stored resources
    </base-button>
    <base-button @click="setSelectedTab('add-resource')" :mode="addResourceBtnMode">Add resource</base-button>
  </base-card>
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import StoredResources from "@/components/learning-resources/StoredResources";
import AddResource from "@/components/learning-resources/AddResource";

export default {
  name: "TheResources",
  components: {StoredResources, AddResource},
  data() {
    return {
      selectedTab: 'stored-resources',
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official Vue.Js documentation.',
          link: 'https://vuejs.org'
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Try googling fo some tips...',
          link: 'https://google.com'
        }
      ]
    }
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
      deleteResource: this.deleteResource
    }
  },
  computed: {
    storedResourcesBtnMode() {
      return this.selectedTab === 'stored-resources' ? null : 'flat'
    },
    addResourceBtnMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat'
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab
    },
    addResource(title, description, link) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: link
      }
      this.storedResources.unshift(newResource)
      this.selectedTab = 'stored-resources'
    },
    deleteResource(resourceId) {
      const resourceIndex = this.storedResources.findIndex(resource => resource.id === resourceId)
      this.storedResources.splice(resourceIndex, 1)
    }
  }
}
</script>

<style scoped>

</style>
