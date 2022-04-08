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
      <router-link
        class="text-decoration-none"
        :to="{ name: 'Home', hash: '#about' }"
        ><v-btn color="#f2542d" outlined class="btn my-8">
          View more
        </v-btn></router-link
      >
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
  height: 100vh;
  width: 100vw;
  padding: 10%;
  background-blend-mode: multiply;
  background-position: center;
  background-size: 80%;
  background-color: #303633;
}

.info_container {
  height: 100%;
  margin-top: 10%;
}
.header {
  font-size: 3.5em;
  color: #f2542d;
  height: 100%;
}
p {
  margin-left: 25px;
  padding: 0;
  font-size: 1.5em;
  font-weight: bolder;
  color: #f15152;
}

.dev_span {
  color: #f2542d;
}

.secondary-text {
  color: #c5c3c6;
}
</style>