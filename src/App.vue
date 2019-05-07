<template>
  <div class="container">
    <div class="row mt-4">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on Item to delete it!
        </div>
      </div>
    </div>
    <app-header :item-count="items.length" :max-items="maxItems"></app-header>
    <app-new-item @itemAdded="addItem"></app-new-item>
    <app-items-layout :items="items" @itemRemoved="removeItem"></app-items-layout>
  </div>
</template>

<script>
import Header from './components/Header';
import ItemsLayout from './components/ItemsLayout';
import NewItem from './components/NewItem';

export default {
  data() {
    return {
      items: [
        `I wan't sex with big sister`
      ],
      maxItems: 10
    }
  },
  components: {
    appItemsLayout: ItemsLayout,
    appNewItem: NewItem,
    appHeader: Header
  },
  methods: {
    addItem(item) {
      if (this.items.length >= this.maxItems) {
        return false;
      }
      this.items.push(item);
    },
      removeItem(index) {
      this.items.splice(index, 1);
    }
  }
 
}
</script>

<style>

</style>
