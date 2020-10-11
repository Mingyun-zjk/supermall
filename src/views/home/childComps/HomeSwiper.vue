<template>
  <Swiper>
    <SwiperItem v-for="(item,index) in banners" :key="index">
      <a :href="item.link">
        <img :src="item.image" alt="" @load="imageLoad">
      </a>
    </SwiperItem>
  </Swiper>
</template>
<script>
  import {Swiper,SwiperItem} from 'components/common/swiper'

  export default {
    name:'HomeSwiper',
    props: {
      banners: {
        type: Array,
        default() {
          return []
        }
      }
    },
    components: {
      Swiper,
      SwiperItem
    },
    data() {
      return {
        isLoad: false
      }
    },
    methods: {
      imageLoad() {
        if(!this.isLoad){
          this.$emit("swiperImageLoad")
          this.isLoad = true
        }
      }
    }
  }
</script>
<style></style>