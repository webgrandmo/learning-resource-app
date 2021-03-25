<template>
  <base-card>
    <template v-slot:card>
      <base-button
        @click="setSelectedTab('resource-list')"
        :mode="storedResBtnMode"
        >Stored Resources</base-button
      >
      <base-button @click="setSelectedTab('add-resource')" :mode="addResBtnMode"
        >Add Resource</base-button
      >
    </template>
  </base-card>
  <component :is="selectedTab"></component>
</template>



<script>
import ResourceList from './ResourceList.vue';
import AddResource from './AddResource.vue';
export default {
  data() {
    return {
      selectedTab: 'resource-list',
      storedResources: [
        {
          id: 'official-docs',
          title: 'Official Documentation',
          description: 'The official Vue.js documentation',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Learn to google',
          description: 'learn how to use google for learning',
          link: 'https://google.com',
        },
      ],
    };
  },
  components: {
    ResourceList,
    AddResource,
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  computed: {
    storedResBtnMode() {
      return this.selectedTab === 'resource-list' ? null : 'flat';
    },
    addResBtnMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>