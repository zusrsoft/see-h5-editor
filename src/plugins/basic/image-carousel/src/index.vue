<!--test.vue-->
<template>
  <div class="see-image-carsousel">
    <!--异步加载轮播图的情况;-->
    <Swiper class="image-carsousel-swiper" v-if="imageSrcList.length > 0" :key="imageSrcList.length" :autoPlay='true'
            :showIndicator='true' :interval="interval" duration="500">
      <Slide class="image-carsousel-slide" v-for="(item,index) in imageSrcList" :key="index">
        <img class="image-carsousel-image" :src="item" alt="">
      </Slide>
    </Swiper>
  </div>
</template>

<script>
import { Swiper, Slide } from 'vue-swiper-component'

export default {
  name: 'SeeImageCarousel', // 这个名字很重要，它就是未来的标签名<see-text></see-text>
  components: {
    Swiper,
    Slide
  },
  props: {
    imageSrcList: {
      type: Array,
      default: () => {
        return [
          'http://seopic.699pic.com/photo/50051/4111.jpg_wh1200.jpg',
          'http://seopic.699pic.com/photo/50051/4111.jpg_wh1200.jpg',
          'http://seopic.699pic.com/photo/50051/4111.jpg_wh1200.jpg'
        ]
      }
    },
    interval: {
      type: Number,
      default: 2500
    }
  },
  watch: {
    imageSrcList (val) {
      console.log('imageSrcList', val)
    }
  },
  data () {
    return {}
  },
  methods: {}
}
</script>

<style lang="scss" scoped>
  .image-carsousel-swiper,
  .image-carsousel-slide,
  .image-carsousel-image {
    display: block;
    width: 100%;
    height: 100%;
  }
</style>
<style>
  .image-carsousel-swiper .wh_swiper {
    height: 100%;
  }
</style>
