<template>
  <base-card>
    <base-button @click="toggleTab('stored-items')">Buckit List</base-button>
    <base-button @click="toggleTab('add-buck-list-item')"
      >Add Buckit</base-button
    >
  </base-card>
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
      listItems: this.storedListItems
    };
  },
  method: {
    toggleTab(tab) {
      this.selectedTab = tab;
      console.log(this.selectedTab);
    }
  }
};
</script>
