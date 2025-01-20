<template>
  <ul class="practice-content-list">
    <li v-for="(s, i) in this.recentFiles">
      <a :href="s.path" class="d-block btn btn-primary">
        {{ i + 1 }}. {{ s.title }}
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    not: String,
    limit: Number,
  },
  data() {
    return {};
  },
  computed: {
    recentFiles() {
      let files = this.$site.pages
          .filter((p) => {
            if (p.path != this.not) {
              return p.path.indexOf("/services/") >= 0;
            }
          })
          /*.sort((a, b) => {
            let aDate = new Date(a.frontmatter.published).getTime();
            let bDate = new Date(b.frontmatter.published).getTime();
            let diff = aDate - bDate;
            if (diff > 0) return -1;
            if (diff < 0) return 1;
            return 0;
          })
          .slice(0, parseInt(this.limit));*/

      return files;
    },
  },
};
</script>

<style lang="stylus">
@require '../websylvain-styles/theme/variables.styl'

</style>
