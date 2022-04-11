<template>
  <div id="about">
    <section class="container">
      <section class="text_container">
        <h2>ABOUT US</h2>
        <p>
          Based out of Houston TX, we are available to ship to almost anywhere
          in the United States. Our reliability and reputation for secure,
          efficient deliveries is our strongest quality, as our reviews will
          attest. We are an all American, trust-worthy, respectful, and reliable
          business. Focusing on these things allows us to better serve our
          customers shipping needs.
        </p>
        <p>
          Running a 2017 GMC Sierra 4x4 that can go just about anywhere, we can
          handle any small freight up to and including boats under 6000 lbs.
          Using our enclosed trailer we also have the ability to transport
          multiple ATV's, Motorcycles and small cars.
        </p>
        <p>
          We provide fast and reliable service, putting emphasis on meeting our
          contractual obligations. Put your trust in us, and you will never need
          to look for another carrier again.
        </p>
      </section>
      <section class="image_container">
        <v-img :src="truck.src"> </v-img>
      </section>
    </section>
  </div>
</template>

<script>
export default {
  name: "about-section",
  data() {
    return {
      truck: {
        src: "./truckandtrailer.JPG",
      },
    };
  },
};
</script>


<style lang="scss" scoped >
.container {
  display: grid;
  place-items: center;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
}
.text_container {
  width: 80%;
}
.image_container {
  display: grid;
  place-items: center;
  margin-top: 5%;
  width: 95%;
}
.v-image {
  width: 90% !important;
  place-self: center;
  justify-items: center;
}

#about {
  height: auto;
  background-color: #303633;
  padding-top: 5%;

  h2 {
    font-weight: bold;
    color: #368f8b;
    font-family: "Bebas Neue", cursive;
    padding-top: 15px;
    font-size: 2em;
  }
  p {
    padding: 10px 10px 10px 0px;
    font-family: "Oxygen", sans-serif;
    font-weight: 400;
    color: #dcedff;
    font-size: 1em;
  }
}
@media screen and (min-width: 700px) {
  #about {
    display: grid;
    place-items: center;
    padding-top: 5%;
    p {
      font-size: 1.5em;
      align-self: start;
    }
    h2 {
      font-size: 3em;
    }
    .container {
      width: 80%;
    }
    .text_container {
      place-self: start;
    }
  }
  .image_container {
    width: 100%;
  }
  .v-image {
    width: auto !important;
  }
}
</style>