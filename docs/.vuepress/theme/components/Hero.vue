<template>
  <div class="intro">
    <div class="intro-left">
      <h1>Hi</h1>
    </div>
    <div class="intro-right">
      <h4>Sylvain Pastor</h4>
      <h2>Developpeur web</h2>
      <h4><span id="typed"></span></h4>
    </div>
  </div>
</template>

<script>
import Typed from "typed.js";

export default {
  data() {
    return {
      options: {
        strings: [
          "Freelance",
          "Etablit en France",
          "Dans l'Aude, à Carcassonne !",
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
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100%;
  transform: translate(-50%, -50%);
  -webkit-transform: translate(-50%, -50%);
  -moz-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  -o-transform: translate(-50%, -50%);

  .intro-left {
      display: inline-block;
      padding-right: 20px;
  }

  .intro-left h1 {
        font-size: 80px;
      color: #fff;
      font-weight: 600;
  }

  .intro-right {
      display: inline-block;
      text-align: left;
      padding-left: 20px;
      position: relative;
  }

  .intro-right:before {
      content: '';
      position: absolute;
      left: 0;
      bottom: 10px;
      height: 89%;
      width: 10px;
      background: #fff;
  }

  .intro-right h4 {
    font-size: 2rem;
    display: inline-block;
  }

  .intro-right h4,
  .intro-right h2 {
      border: none;
      padding: 0px;
      margin: 0;
      color: #fff;
      text-transform: uppercase;
  }
}

@media screen and (min-width: $MQMobile){
    .intro-left h1 {
        font-size: 160px!important;
    }

    .intro-right h2 {
        font-size: 5em!important;
    }
}
</style>
