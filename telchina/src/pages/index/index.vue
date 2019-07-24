<template>
  <div>
    <el-container>
      <el-header class="index-header">
        <index-header></index-header>
      </el-header>
      <el-main class="index-main">
        <carousel :lists="lists"></carousel>
        <mission></mission>
        <news-center></news-center>
        <thematic-plate :plateImg="plateImg"></thematic-plate>
        <classic-case :cases="cases"></classic-case>
        <contact></contact>
      </el-main>
      <el-footer class="index-footer">
        <footer-index :concat="concat"></footer-index>
      </el-footer>
    </el-container>
  </div>
</template>

<script>
import IndexHeader from "./children/index-header.vue";
import Carousel from "./children/carousel.vue";
import Mission from "./children/mission.vue";
import NewsCenter from "./children/news-center.vue";
import ThematicPlate from "./children/thematicPlate";
import ClassicCase from "./children/classic-case";
import Contact from "./children/contact";

import FooterIndex from "../public/footer/footer-index";

import axios from "axios";
export default {
  name: "Index",
  components: {
    IndexHeader,
    Carousel,
    Mission,
    NewsCenter,
    ThematicPlate,
    ClassicCase,
    Contact,
  },
  data() {
    return {
      lists: [],
      plateImg: [],
      cases: [],
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    getData() {
      axios
        .get("api/index.json?t=" + new Date().getTime().toString())
        .then(this.getSuccess);
    },
    getSuccess(res) {
      console.log(res);
      if (!!res.data && res.data.success === true) {
        this.lists = res.data.data;
        this.plateImg = res.data.plateImg;
        this.cases = res.data.cases;
      }
    }
  }
};
</script>

<style lang="less" scoped>
* {
  padding: 0;
}
@bgc-white: #fff;
.index-header {
  background-color: @bgc-white;
  height: 100px !important;
}
.index-main {
  overflow: hidden;
}
.index-footer{
  height: 200px !important;
}
</style>

