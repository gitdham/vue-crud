<template>
  <div id="app">
    <Header />
    <AddItem v-on:add-item="addItem" />
    <Items v-bind:items="items" v-on:del-item="deleteItem" />
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Items from "./components/Items";
import AddItem from "./components/AddItem";

export default {
  name: "App",
  components: {
    Header,
    Items,
    AddItem,
  },
  data() {
    return {
      items: [
        {
          id: 1,
          nm_barang: "Shampoo",
          qty: 2,
          hrg_satuan: 3500,
        },
        {
          id: 2,
          nm_barang: "Sabun",
          qty: 2,
          hrg_satuan: 1500,
        },
        {
          id: 3,
          nm_barang: "Odol",
          qty: 2,
          hrg_satuan: 3000,
        },
      ],
    };
  },
  methods: {
    deleteItem(id) {
      this.items = this.items.filter((item) => item.id !== id);
    },
    addItem(newItem) {
      this.items = [...this.items, newItem];
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
