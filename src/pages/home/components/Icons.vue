<template>
  <div class="home-icons">
    <mt-swipe :auto="0">
      <mt-swipe-item v-for="(list,index) of swiperList" :key="index">
          <div class="icons">
            <div class="icon" v-for="item of list" :key="item.id">
              <img :src="item.imgUrl" >
              <span v-text="item.desc"></span>
            </div>
          </div>
      </mt-swipe-item>
    </mt-swipe>
  </div>
</template>

<script>
export default {
  name: 'Icons',
  props: {
    iconList: Array
  },
  computed: {
    swiperList () {
      let swiperList = []
      this.iconList.forEach((item, index) => {
        var num = Math.floor(index / 8)
        if (swiperList[num] == null) {
          swiperList[num] = []
        }
        swiperList[num].push(item)
      })
      return swiperList
    }
  }
}
</script>

<style lang="stylus" scoped>
    .home-icons
        height 19.2rem
        margin-top .7rem
      .icons
        display: flex
        flex-wrap: wrap
        .icon
            width: 9.3rem
            height: 8.1rem
            display: flex
            justify-content: center
            align-items: center
            flex-wrap: wrap
            flex-direction: column
            img
                height: 5.5rem
                width: 5.5rem
            span
                color: #212121
</style>
