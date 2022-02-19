<template>
  <div>
    <div style="background: hsl(0, 0%, 10%)">
      <div class="container">
        <div>
          <div
            class="jumbotron jumbotron-fluid m-0 py-4 text-left"
            style="background: hsl(0, 0%, 10%); color: white"
          >
            <div>
              <h1 class="m-0 p-0" style="font-weight: 900">KEYSTROKE, INC.</h1>
              <span class="catchphrase">One stop keyboard market</span>
            </div>
          </div>
          <div>
            <nav class="navbar px-0">
              <router-link class="nav-link" to="/">Home</router-link>
              <router-link class="nav-link" to="/">Products</router-link>
              <!-- <div>
            <div v-if="user.photoURL">
              <img
                :src="user.photoURL"
                class="img-thumbnail profile-image"
                alt
              />
              <router-link class="btn btn-primary my-2 my-sm-0" to="/cart">
                <img
                  src="https://pngimg.com/uploads/shopping_cart/shopping_cart_PNG38.png"
                  width="50"
                  alt
                />
                <span class="badge badge-danger badge-pill">{{
                  cart.length
                }}</span>
              </router-link>
            </div>
            <router-link v-else class="btn btn-primary my-2 my-sm-0" to="/login"
              >Login</router-link
            >
          </div> -->
            </nav>
          </div>
        </div>
      </div>
    </div>
    <div class="page-container">
      <router-view />
    </div>
    <div class="jumbotron jumbotron-fluid m-0 py-3">
      <div class="container">
        <h1 class="display-4">Footer</h1>
        <p class="lead">Catchphrase goes here</p>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "Base",
  computed: {
    ...mapGetters("account", ["user"]),
    ...mapGetters("product", ["cart"]),
  },
};
</script>

<style>
span.catchphrase {
  font-family: "IBM Plex Sans", sans-serif;
  font-weight: 300;
  font-size: 18px;
}

nav {
  background-color: hsl(0, 0%, 10%);
}
.navbar-brand {
  font-weight: bold;
  font-size: 25px;
  /* font-family: Comic; */
  color: #ffffff !important;
}
.profile-image {
  width: 50px;
  border-radius: 100% !important;
}
.page-container {
  padding-top: 81px;
}
.btn {
  border-radius: 0%;
  font-weight: bold;
  background: crimson;
  border: crimson;
}
.btn:hover {
  background: lightcoral;
}
input {
  border-radius: 0%;
}
.btn:focus {
  background: lightcoral;
}

h1 {
  font-family: "IBM Plex Mono", monospace;
}

h2,
h3,
h4,
h5,
h6 {
  font-family: "IBM Plex Sans", sans-serif;
}
</style>