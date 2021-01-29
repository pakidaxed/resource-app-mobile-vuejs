<template>
  <teleport to="body">
    <div>
      <dialog open>
        <header>
          <slot name="header">
            <h2>{{ title }}</h2>
          </slot>
        </header>
        <section>
          <slot></slot>
        </section>
        <menu>
          <slot name="actions">
            <base-button @click="$emit('close')">Close</base-button>
          </slot>
        </menu>
      </dialog>
    </div>
  </teleport>
</template>

<script>
export default {
  name: "BaseDialog",
  emits: ['close'],
  props: ['title']
}
</script>

<style scoped>
div {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.75);
  z-index: 10;
}

dialog {
  position: fixed;
  top: 20vh;
  left: 10%;
  width: 80%;
  z-index: 100;
  border-radius: 12px;
  border: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 0;
  margin: 0;
  overflow: hidden;
}

header {
  background-color: crimson;
  color: white;
  width: 100%;
  padding: 15px;
}

header h2 {
  margin: 0;
}

section {
  padding: 15px;
  background-color: white;
}

menu {
  padding: 15px;
  display: flex;
  justify-content: flex-end;
  margin: 0;
  background-color: white;
}

@media (min-width: 768px) {
  dialog {
    left: calc(50% - 300px);
    width: 600px;
  }
}
</style>
