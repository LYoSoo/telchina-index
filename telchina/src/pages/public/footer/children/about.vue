<template>
  <el-row class="main">
    <el-col :span="16" :offset="4" class="main-col">
      <el-row class="concat-about">
        <el-col :span="14" class="concat-left">
            <concat-left></concat-left>
        </el-col>
        <el-col :span="10"></el-col>
      </el-row>
    </el-col>
  </el-row>
</template>

<script>
import ConcatLeft from "./concat-left"
export default {
  name: "About",
  components: {
      ConcatLeft,
  }
};
</script>

<style lang="less" scoped>
.main {
  height: 300px;
  background-color: rgb(52, 61, 68);
  .main-col {
    height: 100%;
    .concat-about {
      height: 100%;
      .concat-left {
        background-color: #faa;
        height: 100%;
      }
    }
  }
}
</style>
