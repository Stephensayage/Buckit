<template>
  <li>
    <base-card>
      <header>
        <h3>{{ title }}</h3>
        <button>Delete</button>
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
  props: ['title', 'desc', 'link']
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

button {
  margin: 0 25px 0 0;
  width: 60px;
  color: white;
  background-color: #e07a5f;
}
button:hover {
  background-color: red;
}

a {
  padding: 20px;
  text-decoration: none;
  color: #3d5a80;
}
a:hover {
  color: #98c1d9;
}
</style>
