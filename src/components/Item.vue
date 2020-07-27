<template>
  <div>
    <td>{{ item.nm_barang }}</td>
    <td>xx</td>
    <td>{{ item.hrg_satuan }}</td>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: ["item"],
};
</script>

<style scoped>
/* .item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc solid;
} */
</style>
