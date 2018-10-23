<template>
  <div>
    <div class="title">周末去那儿</div>
    <ul>
      <li class="item border-bottom" v-for="(item) in list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl"  alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'weekend',
  props: {
    list: Array
  },
  data () {
    return {
      recommendList: [
        {
          id: '001',
          title: '重庆必游top10',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/53/4bcd11cc3a5374.jpg_r_640x214_988a4cee.jpg',
          desc: '重庆必游top10'
        },
        {
          id: '002',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/53/4bcd11cc3a5374.jpg_r_640x214_988a4cee.jpg',
          desc: '泸沽湖三日游泸沽湖三日游泸沽湖三日游泸沽湖三日游泸沽湖三日游'
        },
        {
          id: '003',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/c9/c9ab2722d2990967a3.img.jpg_200x200_b4832539.jpg',
          desc: '泸沽湖三日游'
        },
        {
          id: '004',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/c9/c9ab2722d2990967a3.img.jpg_200x200_b4832539.jpg',
          desc: '泸沽湖三日游'
        },
        {
          id: '005',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/c9/c9ab2722d2990967a3.img.jpg_200x200_b4832539.jpg',
          desc: '泸沽湖三日游'
        },
        {
          id: '006',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/c9/c9ab2722d2990967a3.img.jpg_200x200_b4832539.jpg',
          desc: '泸沽湖三日游'
        },
        {
          id: '007',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/c9/c9ab2722d2990967a3.img.jpg_200x200_b4832539.jpg',
          desc: '泸沽湖三日游'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~style/mixins.styl"
  .title
    line-height .8rem
    background #eee
    text-indent .2rem
  .item-img-wrapper
    overflow hidden
    height 0
    padding-bottom 37.09%
    .item-img
      width 100%
  .item-info
    padding .1rem
    .item-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      color #ccc
      ellipsis()
</style>
