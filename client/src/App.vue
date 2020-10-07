<template>
  <the-header></the-header>
  <stored-items :list-items="storedListItems"></stored-items>
</template>

<script>
import StoredItems from './components/BucketList/StoredItems.vue';
import TheHeader from './components/Layouts/TheHeader.vue';

export default {
  components: {
    StoredItems,
    TheHeader
  },
  data() {
    return {
      storedListItems: [
        {
          id: '1',
          title: 'Offical Guide to Buckit',
          desc:
            'Please create as many bucket list items as you want! Links can be included to resources',
          link: 'https://personalexcellence.co/blog/bucket-list/'
        }
      ]
    };
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
