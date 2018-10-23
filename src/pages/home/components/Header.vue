<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
    输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import {mapState, mapGetters} from 'vuex'
export default {
  name: 'homeHeader',
  computed: {
    ...mapState(['city']),
    ...mapGetters(['doubleCity'])
  }
  // props: {
  //   city: String
  // }
}
</script>
// scoped 只对当前组件样式有效
// 1rem = html font-size = 50px
// 86/100 0.86rem
<style lang="stylus" scoped>
  @import "~style/varibles.style"
  .header
    display: flex
    line-height: .86rem
    background-color: $bgColor
    color #ffffff
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align center
        font-size .4rem
    .header-input
      flex: 1
      height .64rem
      line-height .64rem
      margin-top .12rem
      margin-left .2rem
      padding-left .2rem
      background #fff
      color #ccc
      border-radius .1rem
    .header-right
      min-width: 1.04rem
      padding 0 .1rem
      float: right
      text-align center
      color white
      .arrow-icon
        font-size .24rem

</style>
