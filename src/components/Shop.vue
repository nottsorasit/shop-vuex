<template>
  <div class="contrainer">
    <h3 align="left">รายการสินค้า</h3>
    <div class="row">
      <div class="col-md-2" v-for="item in products" :key="item.id">
        <div class="card h-100">
          <img :src="item.imgUrl" class="card-img-top" :alt="item.title" />
          <div class="card-body">
            <p class="card-title">{{ item.title }}</p>
            <p class="card-text">{{ item.price.toLocaleString() }} บาท</p>
            <hr />

            <button class="btn btn-primary" @click="addCart(item)">
              หยิบใส่ตะกร้า
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";

export default {
  name: "Shop",
  mounted() {
    this.getProducts();
  },
  computed: {
    ...mapGetters(["products"]),
  },
  methods: {
    ...mapActions(["addCart", "getProducts"]),
  },
};
</script>

<style scoped>
</style>
