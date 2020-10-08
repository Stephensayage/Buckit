<template>
  <li>
    <base-card>
      <header>
        <h3>{{ title }}</h3>
        <base-button mode="flat" @click="removeItem(id)">Delete</base-button>
      </header>
      <p>{{ desc }}</p>
      <nav>
        <a :href="link" target="_blank">Link</a>
      </nav>
    </base-card>
  </li>
</template>

<script>
export default {
  components: {},
  props: ['id', 'title', 'desc', 'link'],
  inject: ['removeItem']
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
  font-size: 26px;
  margin: 10px 0;
  padding: 10px;
}

p {
  margin: 10px 0;
  padding: 10px;
}

a {
  padding: 20px;
  text-decoration: none;
  color: rgb(178, 124, 0);
}
a:hover {
  color: rgb(255, 213, 0);
}
</style>
