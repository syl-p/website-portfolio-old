<template>
  <div class="intro">
    <h1>Sylvain Pastor</h1>
    <h2><span id="typed"></span></h2>
  </div>
</template>

<script>
import Typed from "typed.js";

export default {
  data() {
    return {
      options: {
        strings: [
          "Développeur web Freelance",
          "Etablit en France",
          "à Carcassonne (11000 Aude)!",
        ],
        typeSpeed: 50,
        loop: true,
      },
      scrolled: false,
    };
  },
  mounted() {
    var typed = new Typed("#typed", this.options);
  },
  methods: {},
};
</script>

<style src="../websylvain-styles/app.styl" lang="stylus"></style>

<style lang="stylus">
.intro{
  display: flex;
  flex-direction: column;
  justify-items: center;
  align-content: center;
  justify-content: center;
  height: 50vh;
  
  h1 {
    font-size: 50px;
    color: #fff;
    font-weight: 600;
  }
}

@media screen and (min-width: $MQMobile){
  .intro {
    h1 {
      font-size: 80px;
    }
  }
}
</style>
