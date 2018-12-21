<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icons></home-icons>
        <home-hot></home-hot>
    </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeHot from './components/Hot'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeHot
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      console.log(res)
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
