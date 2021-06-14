<template>
  <div class="wrapper">
  <swiper :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" />
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1501/31/31826775e41f6b0b.water.jpg_600x330_f457ede5.jpg'
      },{
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/2003/23/23a8b48c0b65370aa3.img.jpg_600x330_e32e0a31.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 55%
    background: #eee
    .swiper-img
      width :100%
</style>