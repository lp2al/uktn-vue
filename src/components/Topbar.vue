<template>
  <div class="topbar" id="topbar">
    <div class="topbar__main container h-nopad">

      <a href="http://techcitynews.staging.wpengine.com" class="topbar__logo">
        <svg xmlns="http://www.w3.org/2000/svg" width="144" height="30" viewBox="0 0 143.5 29.8">
          <rect x="1.5" y="1.1" width="27.2" height="28.2" fill="#FFF"></rect>
          <path d="M60.3 17.1c0 4.1-0.7 7-2.8 9.2 -2 2.2-5.2 3.5-9.5 3.5 -4.3 0-7.4-1.3-9.5-3.5 -2-2.3-2.8-5.1-2.8-9.2V0h6.9v17.1c0 2.1 0.2 3.7 1.1 4.9 0.9 1.1 2.3 1.8 4.2 1.8 1.9 0 3.3-0.7 4.2-1.8 1-1.2 1.1-2.8 1.1-4.9V0h6.9V17.1z" class="logo"></path>
          <path d="M91 29.4h-8.2l-7.4-12.2 -2.3 2.6v9.7h-6.8V0h6.8v10.7l9.1-10.7h8.2L80 11.7 91 29.4z" class="logo"></path>
          <path d="M113.3 5.5h-7.6v23.9h-6.9V5.5h-7.6V0h22V5.5z" class="logo"></path>
          <path d="M143.5 29.4h-7.1l-12.9-19.9c0 0 0.1 3.5 0.1 6.6v13.3h-6.7V0h7.4l12.6 19.7c0 0-0.1-3.3-0.1-6.4V0h6.7V29.4z" class="logo"></path>
          <path d="M27.2 0H2.6C1.2 0 0 1.2 0 2.6v24.6c0 1.4 1.2 2.6 2.6 2.6h24.6c1.4 0 2.6-1.2 2.6-2.6V2.6C29.8 1.2 28.7 0 27.2 0zM27.2 14.6L19.4 26.5c-0.8 1.2-2.4 1.5-3.6 0.7L4.1 19.5c-1.2-0.8-1.5-2.4-0.7-3.6l7.8-11.8c0.8-1.2 2.4-1.5 3.6-0.7l11.7 7.7C27.6 11.8 28 13.4 27.2 14.6z" class="logo"></path>
        </svg>
      </a>

      <searchbar></searchbar>
      <hamburger></hamburger>

      <nav class="topbar__menu js-topbar-menu">
        <a href="/events">Events</a>
        <a href="/awards">Awards</a>
        <a href="http://techcitynews.staging.wpengine.com/guides">Guides</a>
        <a href="http://techcitynews.staging.wpengine.com/digital-issues">Magazine</a>
        <a href="http://techcitynews.staging.wpengine.com/video">Video</a>
        <a href="http://techcitynews.staging.wpengine.com/subscribe-step-1">Subscribe</a> 
      </nav>

      <span class="topbar__social"> 
        <social-follow></social-follow>
      </span>

    </div>
  <!-- container -->
</div>
</template>

<script>

  import Searchbar    from './Searchbar';
  import Hamburger    from './Hamburger';
  import SocialFollow from './SocialFollow';

  export default {
    name: 'topbar',
    components: {
      Hamburger,
      Searchbar,
      SocialFollow
    }
  }

</script>

<style lang="scss">

.topbar {

  @include clearfix;  
  position:relative;
  background-color:$color-background--soft;
  height:50px;

  &__main { height:100%; }

  &__logo {
    float:left;
    width:32px; height:32px;
    margin-left:15px;
    fill:$color-primary;
    @include vertical-align;
    @include breakpoint($sm) {
      display:none;
    }
  }

  &__menu {
    
    @include clearfix;
    position:absolute;
    width:100%; 
    background-color: $color-background--soft;
    top:50px; left:0;
    overflow:hidden;
    z-index:3;
    max-height:0;
  
    @include breakpoint($sm) {
      @include vertical-align;
      float:left; 
      width:auto;
      max-height:600px;
      padding:0;
      margin-left:15px;
    }

    @include breakpoint($md) {
      margin-left:0;
    }
    
    & > a, span {
      display:block;
      padding:10px 10px 10px 20px;
      border-bottom:1px solid $color-border--mild;
      font-size:14px;
      letter-spacing:0.5px;
      color:$color-copy--xsoft;
      font-weight: $font-weight--medium;

      &:first-child { border-top:1px solid $color-border--mild }

      @include breakpoint($sm) {
        display:inline-block;
        padding-left:0;
        border:none;
        font-size:12px;
        &:first-child { border:none}
      }
    }

    &.is-expanded {
      transition: all 0.2s ease-in-out 0s;
      max-height:600px; //for animation
    } 

  }

  &__menu-toggle {
    float:right;
    margin-right:15px;
    @include breakpoint($sm) {
      display:none;
    }
  }

  &__social { 
    font-size:12px;
    color:$color-copy--xsoft;
    display:none;
    @include breakpoint($sm) {
      display:block;
      @include vertical-align;
      float:right; 
    }
  }
}

</style>
