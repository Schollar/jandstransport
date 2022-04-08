<template>
  <nav class="navigation">
    <div class="hamburger">
      <!-- Using the old school hidden checkbox learned way back in unit 1 -->
      <input type="checkbox" ref="checkbox" />

      <!-- Spans make up the hamburger -->
      <span></span>
      <span></span>
      <span></span>
      <!-- Using a list to display navigation links, also on click we close the menu -->
      <ul class="nav_menu">
        <router-link :to="{ name: 'Home', hash: '#home' }"
          ><li @click="close()">Home</li></router-link
        >
        <router-link to="/#about"><li @click="close()">About</li></router-link>
        <router-link to="/#projects"
          ><li @click="close()">Projects</li></router-link
        >
        <router-link to="/#contact"
          ><li @click="close()">Contact</li></router-link
        >
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "navigation-section",
  components: {},
  methods: {
    // Function that unchecks checkbox to hide menu when user navigates somewhere
    close() {
      var checkbox = this.$refs.checkbox;
      checkbox.checked = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.hamburger {
  display: block;
  position: relative;
  top: 35px;
  left: 25px;
  z-index: 1;
  user-select: none;
  a {
    text-decoration: none;
    color: #f2542d;
  }
  a:hover {
    color: purple;
  }
}

/* Hiding the checkbox and putting it ontop of the hamburger */
.hamburger input {
  display: block;
  width: 40px;
  height: 32px;
  position: absolute;
  top: -7px;
  left: -5px;

  cursor: pointer;

  opacity: 0;
  z-index: 2;
}
/* Making the spans the hamburger */
.hamburger span {
  display: block;
  width: 33px;
  height: 4px;
  margin-bottom: 5px;
  position: relative;
  background: #f2542d;
  border-radius: 3px;
  z-index: 1;
  transform-origin: 4px 0px;
  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1),
    background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), opacity 0.55s ease;
}

.hamburger span:first-child {
  transform-origin: 0% 0%;
}

.hamburger span:nth-last-child(2) {
  transform-origin: 0% 100%;
}

/* animating the hamburger to be an X */
.hamburger input:checked ~ span {
  opacity: 1;
  transform: rotate(45deg) translate(-2px, -1px);
  background: #232323;
}

/* Hide the middle span */
.hamburger input:checked ~ span:nth-last-child(3) {
  opacity: 0;
  transform: rotate(0deg) scale(0.2, 0.2);
}

/* Last span goes opposite direction */
.hamburger input:checked ~ span:nth-last-child(2) {
  transform: rotate(-45deg) translate(0, -1px);
}

.nav_menu {
  position: absolute;
  width: 300px;
  margin: -100px 0 0 -50px;
  padding: 50px;
  padding-top: 125px;
  height: 102vh;
  background: #c5c3c6;
  list-style-type: none;

  transform-origin: 0% 0%;
  transform: translate(-100%, 0);
  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1);
}

.nav_menu li {
  padding: 10px 0;
  font-size: 22px;
}
/* Slide in menu from left */
.hamburger input:checked ~ ul {
  transform: none;
}
.navigation {
  position: fixed;
  z-index: 4;
}
</style>