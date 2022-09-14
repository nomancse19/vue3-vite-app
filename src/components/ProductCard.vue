<template>
  <div class="the-product">
    <div class="the-product__title">
      <div>{{ prop_product.name }}</div>
      <img
        src="../img/star.png"
        v-if="prop_product.addedToFavourite"
        width="25"
        height="25"
        alt="Favour"
        @click="toggleFavourite"
      />
      <img
        src="../img/unstar.png"
        v-else
        @click="toggleFavourite"
        width="25"
        height="25"
        alt="Favour"
      />
    </div>
    <div class="the-product__body">
      <img :src="prop_product.thumbnail" alt="" />
      <p>৳{{ prop_product.price }}</p>
    </div>
    <div class="the-product__footer">
      <button @click="handleAddToCartClick()">Add To Cart</button>
      <button @click="handleBuyNowClick()">Buy Now</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    prop_product: {
      type: Object,
      default: () => ({}),
    },
  },
  data() {
    return {};
  },
  methods: {
    handleBuyNowClick() {
      this.$emit("buy-now-click", this.prop_product);
    },
    handleAddToCartClick() {
      this.$emit("add-to-cart", this.prop_product);
    },
    toggleFavourite() {
      this.$emit("toggle-favourite", this.prop_product);
    },
  },
};
</script>

<style scoped>
.the-product {
  width: 250px;
  min-height: 200px;
  border: 1px solid rgb(2, 96, 2);
  margin: 20px auto;
}
.the-product__title {
  background: rgb(2, 96, 2);
  padding: 5px 11px;
  color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.the-product__body {
  padding: 11px;
}

.the-product__footer {
  background: rgba(192, 191, 191, 0.485);
  text-align: center;
  padding: 10px 10px;
  font-weight: bold;
  color: crimson;
}
</style>
