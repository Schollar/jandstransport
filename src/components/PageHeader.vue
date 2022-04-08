<template>
  <div>
    <v-toolbar dark color="#162130" style="height: 10vh">
      <v-toolbar-title class="white--text">
        <div class="mamae">
          <img
            class="logo"
            src="https://vuetifyjs.com/apple-touch-icon-180x180.png"
            width="50px"
          />
        </div>
      </v-toolbar-title>

      <v-toolbar-items>
        <v-btn flat>Home</v-btn>
        <v-btn flat>About</v-btn>
        <v-btn flat>Contact</v-btn>
      </v-toolbar-items>

      <v-spacer></v-spacer>

      <v-layout row align-center style="max-width: 30vw; min-width: 1vw">
        <v-text-field
          solo
          placeholder="Pesquisar..."
          single-line
          append-icon="search"
          background-color="#202d3f"
          color="white"
          hide-details
        ></v-text-field>
      </v-layout>
    </v-toolbar>
  </div>
</template>

<script>
export default {
  name: "page-header",
};
</script>

<style scoped>
</style>