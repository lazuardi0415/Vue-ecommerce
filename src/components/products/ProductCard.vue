<template>
  <div class="card mb-4 shadow">
    <img :src="product.imageUrl" class="card-img-top product-image" />
    <div class="card-body">
      <div class="pb-3">
        <h5 class="card-title text-left">{{ product.name }}</h5>
        <h4
          class="card-subtitle text-left font-price"
        >
          Rp. {{ product.price }}.000,-
        </h4>
      </div>
      <!-- <router-link
        type="button"
        class="btn btn-primary btn-lg btn-block"
        :to="'/details/' + product.id"
        >Details</router-link
      > -->
      <!-- <router-link
          type="button"
          class="btn btn-primary btn-lg"
          :to="'/details/' + product.id"
        >Details</router-link> -->
      <div class="btn-group btn-block" role="group">
        <router-link
          type="button"
          class="btn btn-primary"
          :to="'/details/' + product.id"
          >Product Details</router-link
        >
        <router-link
          type="button"
          class="btn btn-secondary"
          :to="'/details/' + product.id"
          ><i class="fa-solid fa-cart-arrow-down"></i></router-link
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["product"],
};
</script>

<style>
.card .product-image {
  height: 300px;
}
</style>