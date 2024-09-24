<template lang="html">
  <div class="signature">
    <div class="signature-head">
      <div class="signature-head-picture avatar avatar-md">
        <img :src="$withBase('/img/avatars/'+ signature.frontmatter.avatar)" :alt="signature.title">
        <i class="avatar-presence online"></i>
      </div>
      <p class="signature-head-title">
        Écrit par <a :href="signature.path">{{signature.title}}</a>, le <span>{{this.$page.frontmatter.published}}</span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props:{
    author: String
  },
  computed:{
    signature(){

      let signatures = this.$site.pages.filter(p => {
        if (p.path != this.not){
          return p.path.indexOf('/a-propos/auteurs/') >= 0;
        }
      });

      return signatures.filter(s => s.frontmatter.title == this.author)[0];

    }
  }
}
</script>

<style lang="stylus">
  .signature
    &-head
      width: 100%
      display: flex
      align-items: center
      gap: 15px
      &-title
        flex: 1
        margin: 0

</style>
