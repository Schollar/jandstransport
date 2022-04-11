<template>
  <v-footer id="footer">
    <section class="footer">
      <p class="copyright">
        J&S Trucking LLC
        <v-icon class="copyright_icon" size="18px"> mdi-copyright </v-icon>
        {{ year }}
      </p>
    </section>
  </v-footer>
</template>
<script>
export default {
  name: "footer-section",
  computed: {
    // Function that gets the year, found from vuetify docs
    year() {
      var day = new Date();
      return day.getFullYear();
    },
  },
};
</script>
<style lang="scss" scoped>
#footer {
  background-color: #303633;
  display: grid;
  width: 100vw;
  border-top: 1px solid #041f1e;
}
.footer {
  text-align: center;
}
.copyright {
  margin-top: 5px;
  font-size: 16px;
  color: #dcedff;
  font-weight: bold;
  align-self: start;
  margin-bottom: 0 !important;
}
.copyright_icon {
  color: #dcedff;
  margin-bottom: 4px;
}
</style>
