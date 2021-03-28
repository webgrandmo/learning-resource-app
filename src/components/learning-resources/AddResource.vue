<template>
  <base-card>
    <template v-slot:card>
      <form @submit.prevent="submitData">
        <div>
          <label for="resource-title">Add title</label>
          <input type="text" id="resource-title" ref="titleInput" />
        </div>
        <div>
          <label for="resource-desc">Add description</label>
          <textarea type="text" id="resource-desc" ref="descInput"></textarea>
        </div>
        <div>
          <label for="resource-link">Add link</label>
          <input type="url" id="resource-link" ref="linkInput" />
        </div>
        <div style="margin-top: 1rem">
          <base-button type="submit">Add Resource</base-button>
        </div>
      </form>
    </template>
  </base-card>
</template>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>


<script>
// import BaseCard from '../ui/BaseCard.vue';
export default {
  inject: ['addResource'],
  methods: {
    submitData() {
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDescription = this.$refs.descInput.value;
      const enteredUrl = this.$refs.linkInput.value;

      this.addResource(enteredTitle, enteredDescription, enteredUrl);
    },
  },
};
</script>