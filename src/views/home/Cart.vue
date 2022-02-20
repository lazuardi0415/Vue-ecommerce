<template>
  <div class="container" style="padding: 30px">
    <div class="row d-flex justify-content-center">
      <div class="list-group col-8">
        <a
          v-for="item in cart"
          :key="item.id"
          href="#"
          class="
            list-group-item list-group-item-action
            d-flex
            justify-content-between
            align-items-center
          "
        >
          <img :src="item.imageUrl" alt height="60" width="60" />
          <span class="h4">{{ item.name }}</span>
          <div>
            <span class="font-price">Rp. {{ item.price }}.000,- x {{ item.quantity }}</span>
          </div>
          <div>
            <span class="h4 font-price">Rp. {{ item.price * item.quantity }}.000,-</span>
          </div>
        </a>
        <div
          class="
            list-group-item list-group-item-action
            d-flex
            justify-content-between
            align-items-center
          "
        >
          <span class="h4">Total</span>
          <div>
            <span class="h4 font-price">Rp. {{ totalPrice }},000.-</span>
          </div>
        </div>
        <button
          @click="checkout()"
          type="button"
          class="btn btn-primary btn-lg btn-block mt-4"
        >
          Checkout
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "Cart",
  data() {
    return {
      totalPrice: 0,
    };
  },
  computed: {
    ...mapGetters("product", ["cart"]),
    ...mapGetters("account", ["user"]),
  },
  methods: {
    ...mapActions("product", ["removeCart"]),
    calcPrice() {
      this.cart.forEach((element) => {
        this.totalPrice += element.price * element.quantity;
      });
    },
    checkout() {
      const vm = this;
      setTimeout(() => {
        vm.removeCart();
        alert("Purchase successful!");
        vm.$router.push("/");
      }, 2000);
    },
  },
  mounted() {
    this.calcPrice();
  },
};
</script>

<style>
</style>