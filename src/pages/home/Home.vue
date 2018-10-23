<template>
  <div>
    <homeHeader :city="city"></homeHeader>
    <homeSwiper :list = "swiperList"></homeSwiper>
    <homeIcons :iconList="iconList"></homeIcons>
    <homeRecommend :list="list"></homeRecommend>
    <homeWeekend :list="weekendList"></homeWeekend>
  </div>
</template>

<script>
import homeHeader from './components/Header'
import homeSwiper from './components/Swiper'
import homeIcons from './components/Icons'
import homeRecommend from './components/Recommend'
import homeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'home',
  components: {
    homeHeader: homeHeader,
    homeSwiper: homeSwiper,
    homeIcons: homeIcons,
    homeRecommend: homeRecommend,
    homeWeekend: homeWeekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      list: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      if (res.data.ret && res.data) {
        const data = res.data.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.list = data.recommendList
        this.weekendList = data.weekendList
        // console.log(data)
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style scoped>

</style>
