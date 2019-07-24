<template>
  <el-row class="title-top">
    <el-col :span="8" :offset="4">
      <div class="grid-content bg-purple div-mission">
        <p class="p-mission">
          <span class="span-title">我们的使命：</span>
          <span class="span-text">建设创新型智慧城市</span>
        </p>
        <p class="p-mission">
          <span class="span-title">我们的愿景：</span>
          <span class="span-text">成为城市持续可信赖的合作伙伴</span>
        </p>
        <p class="p-mission">
          <span class="span-title">核心价值观：</span>
          <span class="span-text">为合作伙伴创造价值，从而提升企业和员工的自身价值，更好的回馈社会</span>
        </p>
        <p class="p-mission">
          <span class="span-title">企业精神：</span>
          <span class="span-text">理想 扎实 创新 诚信 共享</span>
        </p>
      </div>
    </el-col>
    <el-col :span="8">
      <div class="grid-content bg-purple div-mission">
          <div class="img-div">
            <img src="https://i.loli.net/2019/07/02/5d1b1f9db883c16619.jpg">
          </div>
      </div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: "Mission"
};
</script>

<style lang="less" scoped>
.div-mission {
  height: 400px;
  border-bottom: 1px solid rgb(221,221,221);
  p:first-child {
    padding-top: 100px;
  }
  .p-mission {
    line-height: 50px;
    font-size: 20px;
    .span-title {
      font-weight: 800;
    }
  }
}
.img-div{
  padding-top: 50px;
}
</style>
