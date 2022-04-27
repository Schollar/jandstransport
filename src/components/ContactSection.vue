<template>
  <section id="contact">
    <section class="container">
      <section class="text_container">
        <h2>Contact</h2>
        <p>Text or Call at:</p>
        <p>(713)-471-9149</p>
        <section class="hidden-lg-and-up">
          <v-btn color="#368f8b" raised tile class="btn mb-4">
            <a href="tel:713-471-9149" class="contact_button">Call Now</a>
          </v-btn>
        </section>

        <p>
          If you would like to contact us for anything at all, feel free to
          write message and I will get back to you as soon as possible
        </p>
      </section>
      <form ref="form" class="form" @submit.prevent="sendEmail">
        <v-text-field
          v-model="name"
          name="name"
          class="text-field my-8"
          placeholder="Name"
          outlined
        >
        </v-text-field>
        <v-text-field
          :rules="emailRules"
          v-model="email"
          name="email"
          class="text-field my-8"
          placeholder="Email"
          outlined
        >
        </v-text-field>
        <v-textarea
          :rules="messageRules"
          name="message"
          v-model="message"
          background-color="#d3d3d3"
          placeholder="Message"
          outlined
        ></v-textarea>
        <v-btn
          outlined
          medium
          @click="sendEmail()"
          :loading="loading"
          class="montserrat btn"
          color="#368f8b"
        >
          Submit
        </v-btn>
      </form>
    </section>
  </section>
</template>

<script>
import emailjs from "emailjs-com";
export default {
  name: "contact-section",
  data() {
    return {
      // Setting up variables, and rules for form inputs, found off vuetify docs
      loading: false,
      name: "",
      nameRules: [(v) => !!v || "Name is required"],
      email: "",
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
      ],
      message: "",
      messageRules: [(v) => !!v || "Message cant be empty"],
    };
  },
  methods: {
    // Function that resets the form.
    reset() {
      this.$refs.form.reset();
    },
    // Following EmailJs docs, we send the form content as an object, also send the name and service of my form on the emailJs website, aswell as my userId and the ref to the form
    sendEmail() {
      try {
        emailjs.sendForm(
          "jstransport",
          "jsform",
          this.$refs["form"],
          "DVlO9CMDD-mJLBo1x",
          {
            name: this.name,
            email: this.email,
            message: this.message,
          }
        );
      } catch (error) {
        console.log(error);
      }
      // Reset form field
      this.reset();
    },
  },
};
</script>

<style scoped lang="scss">
#contact {
  display: grid;
  background-color: #303633;
  gap: 25px;
}
.contact_button {
  text-decoration: none;
  color: #dcedff;
}
.btn {
  width: 40%;
}
.text_container {
  align-self: center;

  h2 {
    font-size: 2em;
    font-family: "Bebas Neue", cursive;
    color: #368f8b;
    margin-top: 15%;
  }

  p {
    width: 95%;
    font-family: "Oxygen", sans-serif;
    font-size: 1em;
    color: #dcedff;
  }
}
.email_container {
  padding-bottom: 3% !important;

  > .v-btn {
    margin-bottom: 3% !important;
  }

  > p {
    margin: 0;
  }
}
.container {
  margin-top: 5%;
  display: grid;
  place-self: center;
  width: 80%;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  margin-bottom: 5%;
  column-gap: 5%;
}

.form {
  .text-field {
    height: 55px;
    background-color: #d3d3d3;
  }

  .btn {
    font-weight: bold;
    border-width: 3px;
    margin-bottom: 10%;
  }
}
@media screen and (min-width: 700px) {
  #contact {
    padding-top: 10%;
  }
  .email {
    text-decoration: none;
    pointer-events: pointer;
    font-size: 1.5em;
  }
  .text_container {
    h2 {
      font-size: 3em;
      margin-top: 0;
    }
    p {
      font-size: 2em;
    }
  }
}
@media screen and (min-width: 915px) {
  #contact {
    margin-top: 0;
  }
  .form {
    justify-self: center;
    align-self: start;
    width: 80%;
  }
}
</style>
