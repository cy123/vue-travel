<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'search'
}
</script>

<style lang="stylus" scoped>
  @import "~style/varibles.style"
  .search
    height .72rem
    background  $bgColor
    padding 0 .1rem
    .search-input
      box-sizing border-box
      padding 0 .1rem
      text-align center
      height .62rem
      line-height .62rem
      width 100%
      border-radius .06rem
</style>
