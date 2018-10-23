<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) in pages" :key="index">
        <div class="icon" v-for="item in page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'homeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        loop: false
      }
    }
  },
  computed: {
    pages: function () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~style/mixins.styl"
  .icons >>> .swiper-container
    height 0
    padding-bottom 50%
  .icons
    overflow hidden
    height 0
    padding-bottom 50%
    margin-top .1rem
    //background green
    .icon
      float left
      position relative
      width 25%
      height 0
      padding-bottom 25%
      //background red
      .icon-img
        position absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        //background blue
        .icon-img-content
          display block
          height 100%
          margin 0 auto
          height 100%
      .icon-desc
        position absolute
        left 0
        right 0
        bottom 0
        height .44rem
        text-align center
        line-height .44rem
        color #333333
        ellipsis()
</style>
