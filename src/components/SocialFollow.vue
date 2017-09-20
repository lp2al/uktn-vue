<template>
  <div class="SocialFollow">
    <a rel="external nofollow" class="SocialFollow__facebook" href="https://www.facebook.com/TechCityNews" target="_blank"><facebook-icon /></a>
    <a rel="external nofollow" class="SocialFollow__google" href="https://plus.google.com/+Techcitynews" target="_blank"><google-icon /></a>
    <a rel="external nofollow" class="SocialFollow__twitter" href="https://twitter.com/techcitynews" target="_blank"><twitter-icon /></a>
    <a rel="external nofollow" class="SocialFollow__youtube" href="https://www.youtube.com/channel/UCJDfsrpfDQy57V6fOzoEwaQ" target="_blank"><linkedin-icon /></a>
  </div>
</template>
<script>

  import TwitterIcon from 'icons/twitter.vue'
  import LinkedinIcon from 'icons/linkedin.vue'
  import GoogleIcon from 'icons/google-plus.vue'
  import FacebookIcon from 'icons/facebook.vue'

  export default {
    name: 'social-follow',
    components: {
      TwitterIcon,
      FacebookIcon,
      GoogleIcon,
      LinkedinIcon
    }
  }


</script>

<style lang="scss">

.SocialFollow {

  display:inline-block;

  & > a {
    display:inline-block;
    width:30px; height:30px;
    margin-right:3px;
    fill: $white;
    font-size:14px !important;
    font-weight:400 !important;
    padding:3px 7.5px;
    border-radius: 4px;

    & > .material-design-icon {
      width:17px;
      height:17px;
    }
 
  }

  &__facebook { background-color: #3B5998; }
  &__twitter  { background-color: #1DA1F2; }
  &__google   { background-color: #DB4437; }
  &__youtube  { background-color: #E62117; }
  &__linkedin { background-color: #0077B5; }

 
}


</style>
