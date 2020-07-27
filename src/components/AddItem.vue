<template>
  <div>
    <form @submit="addItem">
      <input type="text" v-model="nm_barang" name="nm_barang" placeholder="Nama Barang" />
      <input type="number" v-model="qty" name="qty" placeholder="Qyt" />
      <input type="text" v-model="hrg_satuan" name="hrg_satuan" placeholder="Harga Satuan" />
      <input type="submit" value="Submit" class="btn-add" />
    </form>
  </div>
</template>

<script>
import uuid from "uuid";
export default {
  name: "AddItem",
  data() {
    return {
      nm_barang: "",
      qty: 0,
      hrg_satuan: 0,
    };
  },
  methods: {
    addItem(e) {
      e.preventDefault();
      const newItem = {
        id: uuid.v4(),
        nm_barang: this.nm_barang,
        qty: this.qty,
        hrg_satuan: this.hrg_satuan,
      };

      if (this.nm_barang !== "" && this.qty !== 0 && this.hrg_satuan !== 0) {
        this.$emit("add-item", newItem);
        this.nm_barang = "";
        this.qty = 0;
        this.hrg_satuan = 0;
      } else {
        alert("Masukan form dengan benar");
      }
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}

input[name="nm_barang"],
input[name="hrg_satuan"] {
  flex: 3;
  padding: 5px;
}

input[name="qty"] {
  width: 10%;
  padding: 5px;
}

input[type="submit"] {
  flex: 1;
}

.btn-add {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn-add:hover {
  background: #666;
}
</style>
