<template>
  <div>
    <section>
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
    </section>
    <keep-alive>
      <component :is="selectedTab"></component>
    </keep-alive>
  </div>
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
      resources: this.storedListItems,
      addResource: this.addResource,
      removeItem: this.removeItem
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
    },
    addResource(title, desc, url) {
      const newResource = {
        id: new Date().toISOString(),
        title: title,
        desc: desc,
        link: url
      };
      this.storedListItems.push(newResource);
      this.selectedTab = 'stored-items';
    },
    removeItem(itemId) {
      const itemIndex = this.storedListItems.findIndex(
        item => item.id === itemId
      );
      this.storedListItems.splice(itemIndex, 1);
    }
  }
};
</script>

<style scoped>
div {
  width: 100%;
  margin: 50px auto 50px auto;
  height: 50px;
}
section {
  margin: 0 auto;
  width: 70%;
}
</style>
