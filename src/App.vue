<template>
  <the-header app-title="RememberMe"></the-header>
  <resource-list :resources="storedResources"></resource-list>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import ResourceList from './components/learning-resources/ResourceList.vue';
export default {
  components: { ResourceList, TheHeader },
  data() {
    return {
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
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>