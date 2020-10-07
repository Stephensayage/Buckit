<template>
  <ul>
    <bucket-list-item
      v-for="item in listItems"
      :key="item.id"
      :title="item.title"
      :desc="item.desc"
      :link="item.link"
    ></bucket-list-item>
  </ul>
</template>

<script>
import BucketListItem from './BucketListItem.vue';

export default {
  components: {
    BucketListItem
  },
  props: ['list-items']
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 25px auto;
  width: 100%;
}
</style>
