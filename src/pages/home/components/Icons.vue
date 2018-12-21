<template>
  <div class="home-icons">
    <mt-swipe :auto="0">
      <mt-swipe-item v-for="(list,index) of swiperList" :key="index">
          <div class="icons">
            <div class="icon" v-for="item of list" :key="item.id">
              <img :src="item.src" >
              <span v-text="item.des"></span>
            </div>
          </div>
      </mt-swipe-item>
    </mt-swipe>
  </div>
</template>

<script>
export default {
  name: 'Icons',
  data () {
    return {
      iconList: [
        {
          id: '01',
          src: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          des: '景点门票'
        },
        {
          id: '02',
          src: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          des: '一日游'
        },
        {
          id: '03',
          src: 'http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png',
          des: '海滨海岛'
        },
        {
          id: '04',
          src: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          des: '动物植园'
        },
        {
          id: '05',
          src: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          des: '大连必游'
        },
        {
          id: '06',
          src: 'http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
          des: '泡温泉'
        },
        {
          id: '07',
          src: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
          des: '亲子游'
        },
        {
          id: '08',
          src: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
          des: '游乐场'
        },
        {
          id: '09',
          src: 'http://img1.qunarzz.com/piao/fusion/1811/f6/e54fad3ea337b02.gif',
          des: '年终大促'
        },
        {
          id: '10',
          src: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
          des: '全部玩乐'
        }
      ]
    }
  },
  computed: {
    swiperList () {
      var swiperList = []
      this.iconList.forEach((item, index) => {
        var num = Math.floor(index / 8)
        if (swiperList[num] == null) {
          swiperList[num] = []
        }
        swiperList[num].push(item)
      })
      console.log(swiperList)
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
            img
                height: 5.5rem
                width: 5.5rem
            span
                color: #212121
</style>
