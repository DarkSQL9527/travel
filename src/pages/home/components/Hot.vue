<template>
  <div class="hot">
    <div class="hot-title">
      <div class="hot-title-left">
        <img src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png"/>
        <span>本周热门榜单</span>
      </div>
      <div class="hot-title-right">
        <span>全部榜单</span>
        <span>></span>
      </div>
    </div>
    <div class="wrapper" ref="wrapper">
      <ul class="content" ref="tabcontent">
        <li v-for="item in data" :key="item.id" ref="tabitem">
            <img class="img" :src="item.src">
            <span>{{item.des}}</span>
            <span>¥{{item.price}}</span>起
        </li>
      </ul>
      <div class="loading-wrapper"></div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'Hot',
  data () {
    return {
      data: [
        {
          id: '001',
          src: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
          des: '故宫',
          price: 20
        },
        {
          id: '002',
          src: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
          des: '故宫',
          price: 20
        },
        {
          id: '003',
          src: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
          des: '故宫',
          price: 20
        },
        {
          id: '004',
          src: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
          des: '故宫',
          price: 20
        },
        {
          id: '005',
          src: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg',
          des: '故宫',
          price: 20
        }
      ]
    }
  },
  methods: {
    InitTabScroll () {
      let width = 0
      for (let i = 0; i < this.data.length; i++) {
        width += this.$refs.tabitem[i].getBoundingClientRect().width
      }

      this.$refs.tabcontent.style.width = width + 'px'
      this.$nextTick(() => {
        if (!this.scroll) {
          this.scroll = new BScroll(this.$refs.wrapper, {
            startX: 0,
            click: true,
            scrollX: true,
            scrollY: false,
            eventPassthrough: 'vertical'
          })
        } else {
          this.scroll.refresh()
        }
      })
    }
  },
  created () {
    this.$nextTick(() => {
      this.InitTabScroll()
    })
  }
}
</script>

<style lang="stylus" scoped>
    .hot-title
      display flex
      justify-content space-between
      margin 1.2rem
      height 2.2rem
      color #666
      .hot-title-left
        font-size 1.6rem
        color #212121
        img
          height 1.5rem
          width 1.5rem
          margin-top -.5rem
      .hot-title-right
        color #616161
        font-size 1.2rem
    .wrapper
      height: 15.4rem
      margin-left: 1.2rem
      .content
        display: flex
        li
          height: 14.1rem
          width 10rem
          display 0 0 10rem
          margin-right .5rem
        .img
          height: 10rem
          width: 10rem
</style>
