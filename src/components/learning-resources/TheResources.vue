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
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>



<script>
import ResourceList from './ResourceList.vue';
import AddResource from './AddResource.vue';
import BaseButton from '../ui/BaseButton.vue';
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
    BaseButton,
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
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
    addResource(title, description, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: url,
      };
      this.storedResources.unshift(newResource);
      this.selectedTab = 'resource-list';
    },
  },
};
</script>