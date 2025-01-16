<template>
  <header>
    <header class="site-header navbar container">
      <section class="navbar-section">
        <a class="navbar-brand navbar-brand_normal mr-2" :href="$site.base"
          ><img src="../public/img/logo-min-black.png" alt="" srcset=""
        /></a>
        <a class="navbar-brand navbar-brand_reverse mr-2" :href="$site.base"
          ><img src="../public/img/logo-min-black.png" alt="" srcset=""
        /></a>
      </section>
      <NavLinks class="navbar-section" />
      <section class="navbar-section">
        <a @click.prevent="nav" class="cd-nav-trigger">
          <span>Menu</span>
        </a>
        <a
          id="typef_orm_share"
          href="https://sylvain32.typeform.com/to/hP4lpWye"
          data-mode="popup"
          data-hide-headers="true"
          data-hide-footer="true"
          data-submit-close-delay="5"
          target="_blank"
          class="div-coins"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <span>Débuter un projet</span>
          <div class="corner-bottom-left"></div>
          <div class="corner-bottom-right"></div>
        </a>
      </section>
    </header>
    <nav class="asideNav">
      <div id="cd-nav" class="cd-nav">
        <div class="cd-navigation-wrapper columns">
          <div class="column col-sm-12 col-6">
            <NavLinks />
          </div>
          <!-- .cd-half-block -->

          <div class="column hide-sm col-sm-12 col-6">
            <address>
              <ul class="cd-contact-info">
                <li>07 61 74 17 02</li>
                <li>
                  <span>A Carcassonne, Aude 11000</span>
                  <span>Occitanie, FRANCE</span>
                </li>
              </ul>
            </address>
          </div>
          <!-- .cd-half-block -->
        </div>
        <!-- .cd-navigation-wrapper -->
      </div>
      <!-- .cd-nav -->
    </nav>
  </header>
</template>

<script>
import NavLinks from "./NavLinks.vue";

export default {
  data() {
    return {
      isLateralNavAnimating: false,
      scrolled: "no-scrolled",
    };
  },
  components: { NavLinks },
  methods: {
    nav() {
      if (!this.isLateralNavAnimating) {
        this.$emit("navAction");
      }
    },
    showOnScroll() {
      if (window.scrollY > window.innerHeight - 550) {
        this.scrolled = "scrolled";
      } else {
        this.scrolled = "no-scrolled";
      }
    },
  },
};
</script>
