<template>
  <div>
    <title-top>
      <template slot="chinese">经典案例</template>
      <template slot="english">CLASSIC CASE</template>
    </title-top>
    <el-row>
      <el-col class="case-bottom" :span="16" :offset="4">
        <el-row>
          <el-col :span="6" class="case-col" v-for="item of cases" :key="item.index">
            <div class="case-div">
              <img class="img-item" :src="item.imgUrl" />
            </div>
            <p class="case-p">{{item.desc}}</p>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import titleTop from "./title-top";
export default {
  props: {
    cases: Array
  },
  name: "ClassicCase",
  components: {
    titleTop
  }
};
</script>

<style lang="less" scoped>
.case-bottom {
  padding-top: 30px;
}
.case-col{
    box-sizing: border-box;
    border-right: 1px solid #fff;
    height: 300px;
    background-color: rgb(245,245,245);
    .img-item{
        width: 100%
    }
    .case-p{
        padding: 15px 0 0 10px;
    }
}
</style>
