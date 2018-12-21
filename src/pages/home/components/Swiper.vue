<template>
    <div class="home-swiper">
        <mt-swipe>
        <mt-swipe-item v-for="item of swiperList" :key="item.id">
            <img :src="item.imgUrl">
        </mt-swipe-item>
        </mt-swipe>
    </div>
</template>

<script>
export default {
  name: 'Swiper',
  props: {
    swiperList: Array
  }
}
</script>

<style lang="stylus" scoped>
    .home-swiper
        height 10rem
        img
            width: 100%
</style>
