<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="(item) in list" :key="item.id">
        <img class="item-img" :src="item.imgUrl"  alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'recommend',
  props: {
    list: Array
  },
  data () {
    return {
      recommendList: [
        {
          id: '001',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/c9/c9ab2722d2990967a3.img.jpg_200x200_b4832539.jpg',
          desc: '泸沽湖三日游泸沽湖三日游泸沽湖三日游泸沽湖三日'
        },
        {
          id: '002',
          title: '泸沽湖三日游',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/c9/c9ab2722d2990967a3.img.jpg_200x200_b4832539.jpg',
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
    margin-top .2rem
  .item
    overflow hidden
    display flex
    height 1.9rem
    .item-img
      height 1.7rem
      width 1.7rem
      margin .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0 // ...起作用
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color #ccc
        ellipsis()
      .item-button
        line-height .44rem
        margin-top .2rem
        background #ff9300
        border-radius .06rem
        padding 0 .2rem
        color #ffffff
</style>
