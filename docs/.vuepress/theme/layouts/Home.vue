<template>
  <Wrapper>
    <section class="container home page">
      <article id="hero" class="section home-section">
        <Hero />
        <a
          href="#"
          class="home-section-scroll"
          :class="{ visible: !this.scrolled }"
          v-scroll="showOnScroll"
        >
          <span>scroll</span>
          <i class="fa fa-long-arrow-down" aria-hidden="true"></i>
        </a>
      </article>
      <article id="about" class="section home-section container">
        <header
          class="home-section-header"
          data-aos="fade-right"
          data-aos-duration="1000"
        >
          <h2>
            Pastor Sylvain, le développeur Web Indépendant <br />
            qui ne vous laissera jamais seul !
          </h2>
        </header>

        <section class="columns about-content">
          <article class="column col-lg-12 col-6 about-content-text">
            <p class="indent-paragraph">
              <template v-for="p in this.$frontmatter.about">
                {{ p }} <br /><br />
              </template>
            </p>
          </article>
          <aside class="column col-lg-12 col-6 about-content-illustration">
            <div class="columns">
              <div
                class="column col-6"
                data-aos="fade-up"
                data-aos-duration="1000"
              >
                <a href="http://midis.com/" target="_blank">
                  <img src="../../public/img/logo-midiscom.png" />
                </a>
                <a href="http://agence-lesautres.com/" target="_blank">
                  <img src="../../public/img/logo-lesautres.png" />
                </a>
                <a href="http://citedecarcassonne.org" target="_blank">
                  <img src="../../public/img/logo-cite-carcassonne.png"
                /></a>
              </div>
              <div
                class="column col-6"
                data-aos="fade-down"
                data-aos-duration="1000"
              >
                <a target="_blank" href="http://www.aude.fr/"
                  ><img src="../../public/img/logo-dep-aude.jpg"
                /></a>
                <a target="_blank" href="https://www.beproject.fr/"
                  ><img src="../../public/img/beproject.png"
                /></a>
              </div>
            </div>
          </aside>
        </section>
        <section class="columns practice-content">

          <h2 class="column col-12">Services</h2>
          <aside class="column col-lg-12 col-6">
            <div>
              <h3>FRONT END</h3>
              <img src="https://camo.githubusercontent.com/3a5a9bf833091b5d30369f7488f233d786853ddd74551ef85289ce20975b58da/68747470733a2f2f736b696c6c69636f6e732e6465762f69636f6e733f693d74732c6a732c74687265656a732c7675656a732c766974652c7461696c77696e64" 
              data-canonical-src="https://skillicons.dev/icons?i=ts,js,threejs,vuejs,vite,tailwind">
            </div>
            <div>
              <h3>BACK END</h3>
              <img src="https://camo.githubusercontent.com/3450b857981104e8c2f628a98848da6ed01e2096666142b7394804a57d16c391/68747470733a2f2f736b696c6c69636f6e732e6465762f69636f6e733f693d727562792c7261696c732c6e6f64656a732c65787072657373" data-canonical-src="https://skillicons.dev/icons?i=ruby,rails,nodejs,express" style="max-width: 100%;">
            </div>
            <div>
              <h3>BACK END</h3>
              <img src="https://camo.githubusercontent.com/cd57b95581075da713be26345a7d144679d7f6c471fd66ae7acf8616f4eb5c7b/68747470733a2f2f736b696c6c69636f6e732e6465762f69636f6e733f693d6d6f6e676f64622c6d7973716c2c706f737467726573716c2c656c61737469637365617263682c7265646973" data-canonical-src="https://skillicons.dev/icons?i=mongodb,mysql,postgresql,elasticsearch,redis" style="max-width: 100%;">
            </div>
            <div>
              <h3>TOOLS</h3>
              <img src="https://camo.githubusercontent.com/4811efc62325c99ac569465eaee691dcfd72e4869977c8c38dae34bff053c9fc/68747470733a2f2f736b696c6c69636f6e732e6465762f69636f6e733f693d6769742c646f636b65722c6c696e75782c6e67696e78" data-canonical-src="https://skillicons.dev/icons?i=git,docker,linux,nginx" style="max-width: 100%;">
            </div>
          </aside>
          <article class="column col-lg-12 col-6 columns">
            <ul class="column col-lg-12 col-12 practice-content-list">
              <li v-for="(s, i) in this.$frontmatter.services">
                <span>{{ i + 1 }}.</span> {{ s }}
              </li>
            </ul>
          </article>
          <footer class="column col-12"></footer>
        </section>
      </article>
      <article id="projects" class="section home-section">
        <header class="home-section-header">
          <h2>Création d'application web sur mesure</h2>
        </header>
        <section>
          <LastProjects :not="'/projects/'" :limit="3" />
          <a :href="$site.base + 'projects/'" class="btn"
            >Voir plus de projets</a
          >
        </section>
      </article>
      <article id="software-craftman" class="section home-section">
        <header
          class="home-section-header"
          data-aos="fade-right"
          data-aos-duration="1000"
        >
          <h2>
            Software Craftman:<br />
            Professionnalisme, pragmatisme<br />
            et fierté.
          </h2>
        </header>
        <section class="columns about-content">
          <article class="column col-lg-12 col-7">
            <div class="indent-paragraph">
              <p>{{ this.$frontmatter.social_description }}</p>
              <ul class="social-list">
                <li>
                  <a target="_blank" href="https://github.com/Websylvain">
                    <i class="fa fa-github"></i>
                  </a>
                </li>
                <li>
                  <a target="_blank" href="https://twitter.com/websylvain_dev">
                    <i class="fa fa-twitter"></i>
                  </a>
                </li>
                <li>
                  <a
                    target="_blank"
                    href="https://www.linkedin.com/in/websylvain"
                  >
                    <i class="fa fa-linkedin"></i>
                  </a>
                </li>
                <li>
                  <a
                    target="_blank"
                    href="https://www.instagram.com/websylvain.dev"
                  >
                    <i class="fa fa-instagram"></i>
                  </a>
                </li>
              </ul>
            </div>
          </article>
          <aside class="column col-lg-12 col-5">
            <LastNews :not="'/posts/'" :limit="3" :noThumb="true" />
          </aside>
        </section>
      </article>
      <article id="contact" class="section home-section">
        <header class="home-section-header">
          <h2>Envie de collaborer ? N'hésitez pas à me contacter.</h2>
        </header>
        <section class="columns">
          <div class="column col-lg-12 col-6">
            Par téléphone
            <h3>07 61 74 17 02</h3>
          </div>
          <div class="column col-lg-12 col-6">
            Par email
            <h3>
              <a href="mailto:contact@websylvain.com">contact@websylvain.com</a>
            </h3>
          </div>
          <div class="column col-12">
            <a
              id="typef_orm_share"
              href="https://websylvain.typeform.com/to/l2724z"
              data-mode="popup"
              data-hide-headers="true"
              data-hide-footer="true"
              data-submit-close-delay="5"
              target="_blank"
              class="btn typeform-share"
              data-aos="fade-up"
              data-aos-duration="1000"
              >Débuter un projet</a
            >
          </div>
        </section>
      </article>
    </section>
  </Wrapper>
</template>

<script>
import Wrapper from "../components/Wrapper.vue";
import Hero from "../components/Hero.vue";
import scroll from "../directives/scroll.js";
import LastProjects from "../components/LastProjects.vue";
import LastNews from "../components/LastNews.vue";
export default {
  data() {
    return {
      scrolled: false,
      data: this.$frontmatter,
    };
  },
  directives: { scroll },
  components: {
    Wrapper,
    Hero,
    LastProjects,
    LastNews,
  },
  methods: {
    showOnScroll() {
      if (window.scrollY > window.innerHeight - 500) {
        this.scrolled = true;
      } else {
        this.scrolled = false;
      }
    },
  },
  mounted() {
    var qs,
      js,
      q,
      s,
      d = document,
      gi = d.getElementById,
      ce = d.createElement,
      gt = d.getElementsByTagName,
      id = "typef_orm_share",
      b = "https://embed.typeform.com/";
    if (!gi.call(d, id)) {
      js = ce.call(d, "script");
      js.id = id;
      js.src = b + "embed.js";
      q = gt.call(d, "script")[0];
      q.parentNode.insertBefore(js, q);
    }
  },
};
</script>
<style lang="stylus">
.home-section-scroll{
    opacity: 0;
    transition: all 0.5s ease;
    &.visible{
        opacity: 1
    }
}
</style>
