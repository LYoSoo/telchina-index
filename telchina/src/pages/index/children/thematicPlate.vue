<template>
  <el-row class="main-background-color">
    <el-col :span="16" :offset="4">
      <div class="main">
        <title-top>
          <template slot="chinese">专题板块</template>
          <template slot="english">THEMATIC PLATE</template>
        </title-top>
        <el-carousel :interval="3000" type="card" class="carouse">
          <el-carousel-item v-for="item in plateImg" :key="item.id">
            <h3 class="medium">
              <img :src="item.imgUrl" class="img-item" />
            </h3>
          </el-carousel-item>
        </el-carousel>
      </div>
    </el-col>
  </el-row>
</template>

<script>
import TitleTop from "./title-top";
export default {
  props: {
    plateImg: Array
  },
  name: "ThematicPlate",
  components: {
    TitleTop
  }
};
</script>

<style lang="less" scoped>
.main-background-color {
    background-color: rgb(238, 238, 238);
  .main {
    margin-top: 30px;
    height: 500px;
    width: 100%;
    background-color: rgb(238, 238, 238);
  }
  .el-carousel__item h3 {
    font-size: 14px;
    line-height: 300px;
    margin: 0;
  }
  .carouse {
    height: 370px;
    padding-top: 30px;
    .medium {
      width: 100%;
      height: 100%;
      .img-item {
        display: block;
        width: 100%;
        height: 100%;
        margin: 0 auto;
      }
    }
  }
}
</style>
