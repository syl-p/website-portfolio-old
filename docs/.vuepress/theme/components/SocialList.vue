<template>
    <ul class="social-list">
        <li>
            <a target="_blank" href="https://github.com/syl-p">
            <i class="fa fa-github"></i>
            </a>
        </li>
        <li>
            <a target="_blank" href="https://twitter.com/websylvain">
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
            href="https://www.instagram.com/syl-p.coding"
            >
            <i class="fa fa-instagram"></i>
            </a>
        </li>
    </ul>
</template>
<script>
    export default {
        
    }
</script>

<style lang="stylus">

ul.social-list {
    padding: 0px;
    margin: 0px;
    list-style: none;
    display: block;
    clear: both;
    li{
      &:first-child{
        padding: 0px;
      }
      display: inline-block;
      padding: 0px 15px;
      i.fa {
        font-size: 25px;
        display: inline-block;
        width: 25px;
      }
    }
  }
</style>