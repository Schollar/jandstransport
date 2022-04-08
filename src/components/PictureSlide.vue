<template>
  <div class="container">
    <v-carousel hide-delimiters>
      <v-carousel-item
        v-for="(item, i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade-transition"
        transition="fade-transition"
      ></v-carousel-item>
    </v-carousel>
  </div>
</template>

<script>
export default {
  name: "picture-slide",
  data() {
    return {
      items: [
        {
          src: "./boat.JPG",
        },
        {
          src: "./boatandhills.JPG",
        },
        {
          src: "./box.JPG",
        },
        {
          src: "./chopper.JPG",
        },
        {
          src: "./dirtbike.JPG",
        },
        {
          src: "./dirtbikeintruck.JPG",
        },
        {
          src: "./faggio.JPG",
        },
        {
          src: "./faggioandchopper.JPG",
        },
        {
          src: "./guyandboat.JPG",
        },
        {
          src: "./guyinboat.JPG",
        },
        {
          src: "./guyonharley.JPG",
        },
        {
          src: "./harley.JPG",
        },
        {
          src: "./mountain.JPG",
        },
        {
          src: "./streetbike.JPG",
        },
        {
          src: "./streetbikeuncovered.JPG",
        },
        {
          src: "./truckandtrailer.JPG",
        },
        {
          src: "./trucksunset.JPG",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: grid;
  place-items: center;
  background-color: #303633;
}
.v-window {
  width: 80%;
}
</style>