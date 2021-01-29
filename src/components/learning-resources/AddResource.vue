<template>
  <base-dialog v-if="invalidInput" title="Invalid input" @close="confirmError">
    <template #default>
      <p>All fields mus be entered, cannot be blank inputs</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Deserunt doloribus, enim illum ipsa possimus sed.
        Adipisci aliquam aliquid autem cum eaque, illo quia rerum ut. At magni sit ullam voluptatem!</p>
    </template>
  </base-dialog>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" v-model="title"/>
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea id="description" name="description" rows="3" v-model="description"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" v-model="link"/>
      </div>
      <div class="form-control">
        <base-button type="submit">Add resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>

export default {
  name: "AddResource",
  inject: ['addResource'],
  data() {
    return {
      title: '',
      description: '',
      link: '',

      invalidInput: false
    }
  },
  methods: {
    submitData() {
      if (this.title.trim() === '' || this.description.trim() === '' || this.link.trim() === '') {
        this.invalidInput = true
        return
      }
      this.addResource(this.title, this.description, this.link)
      this.title = ''
      this.description = ''
      this.link = ''
    },
    confirmError() {
      this.invalidInput = false
    }

  }

}
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 5px;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 5px;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #872236;
  background-color: #f5d2d9;
}

.form-control {
  margin: 1rem 0;
}
</style>
