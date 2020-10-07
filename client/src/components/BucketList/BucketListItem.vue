<template>
  <li>
    <div>
      <header>
        <h3>{{ title }}</h3>
        <button>Delete</button>
      </header>
    </div>
    <p>{{ desc }}</p>
    <nav>
      <a :href="link" target="_blank">Link</a>
    </nav>
  </li>
</template>

<script>
export default {
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
}

p {
  margin: 10px 0;
}

a {
  text-decoration: none;
  color: rgb(0, 163, 217);
}
a:hover {
  color: rgb(0, 98, 130);
}
</style>
