<template>
  <div class="home">
    <navigation-section></navigation-section>
    <top-section></top-section>
    <picture-slide></picture-slide>
  </div>
</template>

<script>
// @ is an alias to /src
import NavigationSection from "../components/NavigationSection.vue";
import PictureSlide from "../components/PictureSlide.vue";
import TopSection from "../components/TopSection.vue";

export default {
  name: "Home",
  components: {
    NavigationSection,
    TopSection,
    PictureSlide,
  },
};
</script>

    NavigationSection