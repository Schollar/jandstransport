<template>
  <div class="home">
    <top-section></top-section>
    <about-section></about-section>
    <contact-section></contact-section>
    <picture-slide></picture-slide>
    <footer-section></footer-section>
  </div>
</template>

<script>
// @ is an alias to /src
import PictureSlide from "../components/PictureSlide.vue";
import TopSection from "../components/TopSection.vue";
import AboutSection from "../components/AboutSection.vue";
import ContactSection from "../components/ContactSection.vue";
import FooterSection from "../components/FooterSection.vue";

export default {
  name: "Home",
  components: {
    TopSection,
    PictureSlide,
    AboutSection,
    ContactSection,
    FooterSection,
  },
};
</script>

    NavigationSection