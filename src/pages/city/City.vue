<template>
  <div>
    <div class="header">
      城市列表
      <router-link to="/">
        <div class="iconfont city-back">&#xe624;</div>
      </router-link>

    </div>
    <citySearch :cities="cities"></citySearch>
    <cityList
    :cities="cities"
    :hotCities="hotCities"
    :letter="letter"
    >
    </cityList>
    <cityAlphabet
    :cities="cities"
    @change="handleLetterChange"
    >

    </cityAlphabet>
  </div>
</template>

<script>
import axios from 'axios'
import citySearch from './commponents/Search'
import cityList from './commponents/List'
import cityAlphabet from './commponents/Alphabet'
export default {
  name: 'city',
  components: {
    citySearch: citySearch,
    cityList: cityList,
    cityAlphabet: cityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.handleGetCityInfo)
    },
    handleGetCityInfo (res) {
      if (res.data.ret && res.data.data) {
        const data = res.data.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterChange (letter) {
      // console.log(letter)
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>
  @import "~style/varibles.style"
  .header
    position relative
    font-size .36rem
    height 0.86rem
    line-height .86rem
    text-align center
    background $bgColor
    color #ffffff
    .city-back
      width .64rem
      position absolute
      top 0
      left 0
      font-size .4rem
      color #ffffff
</style>
