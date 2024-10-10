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
          <header class="column col-12">
            <h2>Bien plus qu'un développeur, votre partenaire...</h2>
            <div
              class="indent-paragraph"
              data-aos="fade-left"
              data-aos-duration="1000"
            >
              <p>{{ this.$frontmatter.services_description }}</p>
            </div>
          </header>
          <article class="column col-lg-12 col-7" style="margin-bottom: 25px">
            <ul class="column col-lg-12 col-12 practice-content-list">
              <li v-for="(s, i) in this.$frontmatter.services">
                <span>{{ i + 1 }}.</span> {{ s }}
              </li>
            </ul>
          </article>
          <aside class="column col-lg-12 col-5">
            <div>
              <h3>Mes Technologies préférées:</h3>
              <ul style="padding-left: 0; margin-left: 0">
                <li v-for="s in this.$frontmatter.services_2">
                  {{ s }}
                </li>
              </ul>
            </div>
          </aside>

          <div
            class="column col-lg-12 col-12 langage-list text-center div-coins"
          >
            <img src="../../public/img/webpack.png" />
            <img src="../../public/img/vuejs.png" />
            <img src="../../public/img/nodejs.png" />
            <img src="../../public/img/mongodb.png" />
            <img src="../../public/img/git.png" />
            <img src="../../public/img/docker.png" />

            <div class="corner-bottom-left"></div>
            <div class="corner-bottom-right"></div>
          </div>
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
            Sur les réseaux
            <SocialList />
          </div>
          <div class="column col-12">
            <a
              id=""
              href="https://sylvain32.typeform.com/to/hP4lpWye"
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
import SocialList from "../components/SocialList.vue";
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
    SocialList,
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
