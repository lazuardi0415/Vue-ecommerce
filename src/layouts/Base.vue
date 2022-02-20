<template>
  <div>
    <!-- Header stuff -->
    <div class="shadow bgcolor" style="background: hsl(0, 0%, 15%)">
      <div class="container">
        <div>
          <!-- Header jumbotron -->
          <div class="m-0 py-4 text-center bgcolor" style="color: white">
            <div>
              <h1 class="m-0 p-0 font-price" style="font-weight: 900">
                KEYSTROKE, INC.
              </h1>
              <span class="catchphrase">One stop keyboard market</span>
            </div>
          </div>
          <!-- end of header jumbotron -->
          <div class="sticky-top">
            <nav class="nav justify-content-center">
              <router-link class="nav-link" to="/">HOME</router-link>
              <router-link class="nav-link" to="/">PRODUCTS</router-link>
              <div>
                <div v-if="user.photoURL">
                  <router-link class="nav-link" to="/cart"
                    >CART({{ cart.length }})
                  </router-link>
                </div>
                <router-link v-else class="nav-link" to="/login"
                  >LOGIN</router-link
                >
              </div>
            </nav>
          </div>
        </div>
      </div>
    </div>

    <!-- Page router -->
    <div class="page-container d-flex flex-column h-100">
      <router-view />
    </div>

    <!-- Footer -->
    <footer class="footer mt-auto py-3">
      <div class="container">
        <span class="text-muted"
          >(C) 2022 Keystroke, Inc. All Rights Reserved</span
        >
      </div>
    </footer>
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
a.nav-link {
  font-family: "IBM Plex Mono", sans-serif;
  font-weight: 400;
  font-size: 24px;
  color: white;
}

span.catchphrase {
  font-family: "IBM Plex Sans", sans-serif;
  font-weight: 300;
  font-size: 18px;
}

.bgcolor {
  background-color: hsl(0, 0%, 15%);
}

.bg-cart {
  width: 100%;
  background-color: crimson;
  border-radius: 50%;
  display: inline-block;
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

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "IBM Plex Sans", sans-serif;
}

.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  margin: 0;
  padding: 0;
}

.font-price {
  font-family: "IBM Plex Mono", monospace;
}
</style>