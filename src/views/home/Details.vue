<template>
  <div class="container p-5">
    <div class="row d-flex justify-content-center">
      <div class="col-6">
        <div class="card shadow">
          <img class="card-img-top" :src="product.imageUrl" alt />
        </div>
      </div>
      <div class="col-6 text-left text-justify">
        <h5>BRAND NAME {{ product.typeVariant }}</h5>
        <h1>{{ product.name }}</h1>
        <p class="text-justify" style="font-weight: 500; font-size: 1.25rem">
          {{ product.content }}
        </p>
        <div>
          <p class="h2 font-price">Rp. {{ product.price }},000.-</p>
        </div>
        <AddToCart :product="product" v-if="user.uid" />
        <router-link
          v-else
          class="nav-link btn btn-primary btn-lg btn-block mt-3"
          to="/login"
          type="button"
          >LOGIN TO PURCHASE</router-link
        >
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
import AddToCart from "../../components/details/AddToCart";
export default {
  data() {
    return {
      isInCardProp: false,
    };
  },
  computed: {
    ...mapGetters("account", ["user"]),
    ...mapGetters("product", ["product"]),
  },
  components: { AddToCart },
  methods: {
    ...mapActions("product", ["productDetails"]),
  },
  mounted() {
    this.productDetails(this.$route.params.idProduct);
  },
};
</script>

<style>
.container-fluid {
  padding: 30px;
}
.image-product {
  width: 100%;
}
.card * {
  max-height: 85vh;
}
</style>