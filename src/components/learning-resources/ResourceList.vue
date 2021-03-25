<template>
  <ul v-if="resources.length">
    <resource-item
      v-for="r in resources"
      :key="r.id"
      :id="r.id"
      :resource-title="r.title"
      :resource-desc="r.description"
      :resource-link="r.link"
    ></resource-item>
  </ul>
</template>

<script>
import ResourceItem from './ResourceItem.vue';
export default {
  components: {
    ResourceItem,
  },
  inject: ['resources'],
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>