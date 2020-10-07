<template>
  <div>
    <base-card>
      <base-button
        @click="setSelectedTab('stored-items')"
        :mode="toggleStoredMode"
        >Buckit List</base-button
      >
      <base-button
        @click="setSelectedTab('add-buck-list-item')"
        :mode="toggleAddMode"
        >Add Buckit</base-button
      >
    </base-card>
  </div>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredItems from './StoredItems.vue';
import AddBuckListItem from './AddBuckListItem';

export default {
  components: {
    StoredItems,
    AddBuckListItem
  },
  data() {
    return {
      selectedTab: 'stored-items',
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
  },
  provide() {
    return {
      resources: this.storedListItems
    };
  },
  computed: {
    toggleStoredMode() {
      return this.selectedTab === 'stored-items' ? null : 'toggled';
    },
    toggleAddMode() {
      return this.selectedTab === 'add-buck-list-item' ? null : 'toggled';
    }
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    }
  }
};
</script>

<style scoped>
div {
  margin: 50px auto 50px auto;
  width: 230px;
  height: 50px;
}
</style>
