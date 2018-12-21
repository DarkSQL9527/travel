<template>
    <div class="home-swiper">
        <mt-swipe>
        <mt-swipe-item v-for="item of swiperList" :key="item.id">
            <img :src="item.src">
        </mt-swipe-item>
        </mt-swipe>
    </div>
</template>

<script>
export default {
  name: 'Swiper',
  data () {
    return {
      swiperList: [
        {
          id: 1,
          src: 'http://img1.qunarzz.com/piao/fusion/1809/9b/bc156ee536900302.jpg_750x200_51b1e9c4.jpg'
        },
        {
          id: 2,
          src: 'http://img1.qunarzz.com/piao/fusion/1812/47/a51fe403715df102.jpg_750x200_085792b6.jpg'
        },
        {
          id: 3,
          src: 'http://img1.qunarzz.com/piao/fusion/1811/f7/72ce947f4dff4c02.jpg_750x200_aa583dba.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
    .home-swiper
        height 10rem
        img
            width: 100%
</style>
