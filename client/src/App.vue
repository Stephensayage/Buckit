<template>
  <the-header></the-header>
  <toggle-list-or-add></toggle-list-or-add>
</template>

<script>
// import StoredItems from './components/BucketList/StoredItems.vue';
import TheHeader from './components/Layouts/TheHeader.vue';
import ToggleListOrAdd from './components/BucketList/ToggleListOrAdd.vue';

export default {
  components: {
    TheHeader,
    ToggleListOrAdd
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Nunito', sans-serif;
}

body {
  margin: 0;
}
</style>
