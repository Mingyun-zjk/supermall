<template>
  <div class="detail">
    <DetailNavBar />
    <DetailSwiper :top-images="topImages"></DetailSwiper>
    <!-- <DetailBaseInfo></DetailBaseInfo> -->
  </div>
</template>
<script>
  import DetailNavBar from './childComps/DetailNavBar'
  import DetailSwiper from './childComps/DetailSwiper'
  // import DetailBaseInfo from './childComps/DetailBaseInfo'

  import {getDetail} from "network/detail"

  export default {
    name:'Detail',
    components: {
      DetailNavBar,
      DetailSwiper,
      // DetailBaseInfo
    },
    data() {
      return {
        iid: null,
        topImages: []
      }
    },
    created() {
      // 1.保存传入的iid
      this.iid = this.$route.params.iid

      // 2.根据iid请求详情数据
      getDetail(this.iid).then(res => {
        // 1.获取顶部的轮播数据
        console.log(res)
        this.topImages = res.result.itemInfo.topImages
      })
    }
  }
</script>
<style></style>