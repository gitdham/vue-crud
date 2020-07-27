<template>
  <div>
    <table>
      <tr>
        <th>Nama Barang</th>
        <th>Qty</th>
        <th>Harga Satuan</th>
        <th>Total</th>
        <th>Aksi</th>
      </tr>
      <tr v-for="item in items" v-bind:key="item.id">
        <td>{{ item.nm_barang }}</td>
        <td>{{ item.qty }}</td>
        <td>{{ item.hrg_satuan }}</td>
        <td>
          <b>{{ item.hrg_satuan*item.qty }}</b>
        </td>
        <td>
          <button class="btn-edit">Edit</button>
          <button class="btn-delete" @click="$emit('del-item', item.id)">Delete</button>
        </td>
      </tr>
    </table>

    <!-- <div v-for="item in items" v-bind:key="item.id">
      <Item v-bind:item="item" />
    </div>-->
  </div>
</template>

<script>
// import Item from "./Item";

export default {
  name: "Items",
  components: {
    // Item,
  },
  props: ["items"],
};
</script>

<style scoped>
table {
  border-collapse: collapse;
  width: 100%;
}

th,
td {
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #f2f2f2;
}

th {
  background-color: #4caf50;
  color: white;
  text-align: center;
}

td + td {
  text-align: center;
}
</style>
