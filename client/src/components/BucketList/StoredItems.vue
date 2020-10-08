<template>
  <div>
    <ul>
      <bucket-list-item
        v-for="item in resources"
        :key="item.id"
        :id="item.id"
        :title="item.title"
        :desc="item.desc"
        :link="item.link"
      ></bucket-list-item>
    </ul>
  </div>
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
  width: 90%;
}
</style>
