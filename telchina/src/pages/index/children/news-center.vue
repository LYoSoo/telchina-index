<template>
  <div>
    <title-top>
      <template slot="chinese">新闻中心</template>
      <template slot="english">NEWS CENTER</template>
    </title-top>
    <el-row class="news-detail">
      <el-col :span="8" :offset="4">
        <img class="img-item" src="https://i.loli.net/2019/07/02/5d1b259f2507795989.jpg" />
      </el-col>
      <el-col :span="8" class="news-right">
        <el-tabs v-model="activeName" @tab-click="handleClick" class="tabs-menu">
          <el-tab-pane label="新闻动态" name="news">
            <news-list :newsTitle="newsTitle" :newsList="newsList"></news-list>
          </el-tab-pane>
          <el-tab-pane label="媒体关注" name="attention">
            <news-list :newsTitle="newsTitle" :newsList="newsList"></news-list>
          </el-tab-pane>
          <el-tab-pane label="行业聚焦" name="focus">
            <news-list :newsTitle="newsTitle" :newsList="newsList"></news-list>
          </el-tab-pane>
          <el-tab-pane label="泰华之家" name="home">
            <news-list :newsTitle="newsTitle" :newsList="newsList"></news-list>
          </el-tab-pane>
        </el-tabs>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import newsList from "./newsList";
import TitleTop from './title-top';
import axios from "axios";
export default {
  name: "NewsCenter",
  components: {
    newsList,
    TitleTop,
  },
  data() {
    return {
      activeName: "news",
      names: "",
      newsList: [],
      newsTitle: [],
      data: {}
    };
  },
  mounted() {
    this.getDate();
  },
  methods: {
    handleClick(tab, event) {
      this.names = event.target.id.slice(4);
      this.newsTitle = this.data[this.names].slice(0, 1);
      this.newsList = this.data[this.names].slice(0);
    },
    getDate() {
      axios
        .get("api/news.json?t=" + new Date().getTime().toString())
        .then(data => {
          if (!!data.data && data.status === 200) {
            this.data = data.data;
            this.newsTitle = this.data['news'].slice(0, 1);
            this.newsList = this.data['news'].slice(0);
          }
        });
    }
  }
};
</script>

<style lang="less" scoped>

.news-detail {
  padding-top: 40px;
  .img-item {
    width: 100%;
  }
}
.news-right {
  padding-left: 20px;
}
</style>
