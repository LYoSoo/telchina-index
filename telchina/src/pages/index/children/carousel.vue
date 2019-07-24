<template>
  <div class="block">
    <el-carousel trigger="click" height="500px" class="aaa">
      <el-carousel-item  v-for="item of lists" :key="item.id"> 
        <el-row>
          <el-col :span="24">
            <img :src='item.imgUrl' />
          </el-col>
        </el-row>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
export default {
  name: "Carousel",
  props: {
    lists: Array
  }
};
</script>

<style lang="less" scoped>
    .aaa{
      line-height: normal
    }
</style>
