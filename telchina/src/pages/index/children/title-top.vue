<template>
  <div class="news-title">
    <p class="news-zh">
      <slot name="chinese"></slot>
    </p>
    <p class="news-en">
      <slot name="english"></slot>
    </p>
  </div>
</template>

<script>
export default {
  name: "TitleTop"
};
</script>

<style lang="less" scoped>
.news-title {
  margin: 0 auto;
  width: 150px;
  text-align: center;
  .news-zh {
    font-size: 26px;
    padding-top: 40px;
  }
  .news-en {
    padding-top: 20px;
    font-size: 18px;
  }
}
</style>
