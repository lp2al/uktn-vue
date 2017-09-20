<template>
  <i class="topbar__menu-toggle hamburger js-hamburger" id="hamburger">
    <span></span>
    <span></span>
    <span></span>
  </i>
</template>
asdasdas
<script>
  export default {
    name: 'hamburger'
  }
</script>

<style lang="scss">

.hamburger {

  @include vertical-align;
  width: 27px; height: 20px;
  transform: rotate(0deg) translateY(-50%);
  transition: .5s ease-in-out;
  cursor: pointer;

  & > span {
    position: absolute;
    width: 100%; height: 3px;
    background: $color-copy--xsoft;
    opacity: 1;
    left: 0;
    transform: rotate(0deg);
    transition: .25s ease-in-out;
    transform-origin: left center;

    &:nth-child(1) { top: 0px;  }
    &:nth-child(2) { top: 9px;  }
    &:nth-child(3) { top: 18px; }
  }

  &.open {
    & > span {
      &:nth-child(1) {
          transform: rotate(45deg);
          top: 0px;
          left: 2px;
      }
      &:nth-child(2) {
          width: 0%;
          opacity: 0;
      }
      &:nth-child(3) {
          transform: rotate(-45deg);
          top: 19px;
          left: 2px;
      }
    }
  }
}

</style>
