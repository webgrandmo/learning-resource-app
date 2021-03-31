<template>
  <teleport to="body">
    <div @click="$emit('close-dialog')">
      <dialog open>
        <header>
          <slot name="header"></slot>
        </header>
        <section>
          <slot name="actions"></slot>
        </section>
      </dialog>
    </div>
  </teleport>
</template>

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
header {
  color: #fff;
  background: #3a0061;
  border-top-left-radius: 9px;
  border-top-right-radius: 9px;
  padding: 0.5rem;
}

h2 {
  margin: 0;
}
section {
  padding: 1rem;
}
dialog {
  text-align: center;
  padding: 0;
  position: fixed;
  top: 30vh;
  /* left: 20%; */
  width: 60%;
  margin: 0 auto;
  border: none;
  border-radius: 9px;
  background: #fff;
  box-shadow: 0 0 15px rgb(148, 148, 148);
}
</style>