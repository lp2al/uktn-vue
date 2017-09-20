<template>
  <div class="search">
    <div class="search-bar js-search">
      <form action="http://techcitynews.staging.wpengine.com" class="search-bar__form" method="get" role="search">
        <input type="search" title="Search for:" name="s" value="" placeholder="Search">
      </form>
      <i class="search-bar__close icon-cross js-search-toggle"></i>
    </div>
    <i class="search-toggle icon-search js-search-toggle"></i>  
  </div>
</template>

<script>
export default {
  name: 'searchbar'
}
</script>

<style lang="scss">

.search-bar {
  transition: all 0.1s linear 0s;
  border-bottom:1px solid $color-border;
  border-top:1px solid $color-border;
  position:absolute;
  width:100%; height:50px; 
  overflow:hidden;
  background-color:$white;
  z-index:0;
  opacity:0;
  transform: scale(0);

  &.is-active {
    opacity:1;
    z-index:9999;
    transform: scale(1);
  }
  
  &__close {
    @include vertical-align;
    font-size:24px; 
    cursor:pointer; 
    position:absolute;
    right:10px;
    z-index:20;
  }

  &__form {
    box-sizing:border-box;
    //position:absolute;
    width:100%;
    left:0; top:0;
    white-space:nowrap;
    font-size:14px;
    height:50px;
    > input {
      height:48px;
      padding:0 20px;
      border:0;
    }
  }
}

.search-toggle {
  @include vertical-align;
  float:right;
  font-size:22px; 
  cursor:pointer; 
  margin-left:10px;
  margin-right:10px;
  color:$color-copy--xsoft;
}

</style>
