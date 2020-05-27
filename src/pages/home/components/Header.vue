<template>
    <div class="home-header">
        <div class="header-back">
            <span class="iconfont backArrow">&#xe624;</span>
        </div>
        <div class="header-input">
            <span class="iconfont magnifier">&#xe632;</span>
            <span>输入城市/景点/游玩主题</span>
        </div>
        <div class="header-address">
            <span class="placeBtn">大连</span>
            <span class="iconfont downArrow">&#xe644;</span>
        </div>
    </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang='stylus' scoped>
    .home-header
        height: 4.4rem
        background-color: rgb(0,188,212)
        display: flex
        align-items: center
        justify-content: space-between
        .header-back
            width: 4.1rem
            display: flex
            align-items: center
            .backArrow
                font-size: 1.7rem
                margin-left: .7rem
                font-weight: 800
        .header-input
            height: 3rem
            background-color: rgb(255,255,255)
            flex: 1
            display: flex
            align-items: center
            color: #e4e7ea
            border-radius: .2rem
            .magnifier
                font-size: 1.7rem
                margin: 0 .7rem
        .header-address
            display: flex
            width: 6.4rem
            justify-content: center
            align-content: center
            .downArrow
                font-size: 1.5rem

</style>
