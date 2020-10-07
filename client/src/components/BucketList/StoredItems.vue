<template>
  <ul>
    <bucket-list-item
      v-for="item in resources"
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
  inject: ['resources'],
  components: {
    BucketListItem
  }
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 25px auto;
  width: 100%;
}
</style>
