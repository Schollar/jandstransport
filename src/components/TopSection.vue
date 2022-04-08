<template>
  <section class="banner">
    <section class="info_container">
      <section>
        <h1 class="header ma-0 pa-0">J & S Trucking LLC</h1>
        <h2 class="secondary-text">
          Taking care of all your <span class="dev_span">Delivery</span> needs
          across America
        </h2>
      </section>
      <!-- m - applies margin, y - applies the spacing for both *-top and *-bottom thats why class of my-8 here -->
      <section class="button_container">
        <router-link
          class="text-decoration-none"
          :to="{ name: 'Home', hash: '#about' }"
          ><v-btn color="#368f8b" outlined class="btn y-8">
            Learn more
          </v-btn></router-link
        >
        <p>Or</p>
        <router-link
          class="text-decoration-none"
          :to="{ name: 'Home', hash: '#contact' }"
          ><v-btn color="#368f8b" outlined class="btn y-8">
            Contact Us
          </v-btn></router-link
        >
      </section>
    </section>
  </section>
</template>


<script>
export default {
  name: "top-section",
  data() {
    return {
      mountain: {
        src: "/wide.JPG",
      },
    };
  },
};
</script>


<style lang="scss" scoped>
.banner {
  text-align: center;
  display: grid;
  place-items: center;
  height: 100vh;
  width: 100vw;
  padding: 10%;
  background-blend-mode: multiply;
  background-position: center;
  background-size: 80%;
  background-color: #303633;
}

.info_container {
  margin-top: 10%;
}
.header {
  font-size: 3.5em;
  color: #368f8b;
  height: 100%;
  font-family: "Bebas Neue", cursive;
}

.dev_span {
  color: #368f8b;
}

.secondary-text {
  color: #dcedff;
  font-family: "Oxygen", sans-serif;
}
.button_container {
  margin-top: 15%;
  > p {
    font-size: 1em;
    color: #dcedff;
    margin: 5%;
    font-family: "Oxygen", sans-serif;
  }
}
</style>