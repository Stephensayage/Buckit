<template>
  <ul>
    <bucket-list-item
      v-for="item in storedListItems"
      :key="item.id"
      :title="item.title"
      :desc="item.desc"
      :link="item.link"
    ></bucket-list-item>
  </ul>
</template>

<script>
import BucketListItem from './components/BucketList/BucketListItem.vue';

export default {
  components: {
    BucketListItem
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
