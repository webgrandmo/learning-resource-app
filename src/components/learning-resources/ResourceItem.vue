<template>
  <li>
    <base-card>
      <template v-slot:card>
        <header>
          <h3>{{ resourceTitle }}</h3>
          <base-button type="button" mode="flat">Delete</base-button>
        </header>

        <p>{{ resourceDesc }}</p>
        <nav>
          <a :href="resourceLink" target="_blank">Learn more</a>
        </nav>
      </template>
    </base-card>
  </li>
</template>

<script>
export default {
  name: 'ResourceItem',
  props: {
    id: {
      type: String,
      required: true,
    },
    resourceTitle: {
      type: String,
      required: true,
    },
    resourceDesc: {
      type: String,
      required: true,
    },
    resourceLink: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}

a:hover,
a:active {
  color: #c89300;
}
</style>