<template>
  <el-row class="title-top">
    <el-col :span="2" :offset="4">
      <div class="grid-content bg-purple">
        <div class="index-header-img">
          <img class="index-header-inner" src="@/assets/image/index/logo.jpg" />
        </div>
      </div>
    </el-col>
    <el-col :span="2" v-for="item of titleList" :key="item.index">
      <div class="grid-content bg-purple title-item">{{item.name}}</div>
    </el-col>
    <el-col :span="1" :offset="1">
      <div class="english">ENGLISH</div>
    </el-col>
    <el-col :span="3"  class="search">
      <el-input>
        <el-button slot="append" icon="el-icon-search"></el-button>
      </el-input>
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: "IndexHeader",
  data() {
    return {
      titleList: [
        { id: "001", name: "首页" },
        { id: "001", name: "关于我们" },
        { id: "001", name: "新闻中心" },
        { id: "001", name: "解决方案" },
        { id: "001", name: "投资者关系" }
      ]
    };
  }
};
</script>

<style lang="less" scoped>
@bgc-white: #fff;
.title-top {
  margin-top: 10px;
}
.index-header-img {
  width: 130px;
  height: 80px;
  .index-header-inner {
    width: 100%;
    height: 100%;
  }
}
.title-item {
  line-height: 80px;
  text-align: center;
  color: rgb(137, 137, 137);
  font-size: 19px;
}
.english {
  line-height: 80px;
}
.search {
  margin-top: 20px
}
</style>
