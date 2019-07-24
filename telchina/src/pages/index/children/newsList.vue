<template>
  <div>
    <el-row class="newsTitle" v-for="(item, index) of newsTitles" :key="index">
      <el-col :span="5" class="el-date">
        <div class="date-detail">{{item.date}}</div>
      </el-col>
      <el-col :span="19" class="el-desc">
        <div class="grid-content bg-purple-light">
          {{item.desc}}
          <p>...[详细]</p>
        </div>
      </el-col>
    </el-row>
    <!-- <li v-for="item of otherNews" :key="item.id"> -->
    <li v-for="item of newsLists" :key="item.id" class="news-bottom">
      <img src="https://i.loli.net/2019/07/11/5d26d26b96d8556299.jpg" />
      <span class="item-desc">{{item.desc}}</span>
      <span class="item-date">{{item.date}}</span>
    </li>
  </div>
</template>

<script>
export default {
  name: "newsList",
  props: {
    newsList: Array,
    newsTitle: Array
  },
  data() {
    return {};
  },
  computed: {
    newsTitles() {
      let newsTitles = [];
      return (newsTitles = this.newsTitle);
    },
    newsLists() {
      let newsLists = [];
      return (newsLists = this.newsList);
    }
  }
};
</script>

<style lang='less' scoped>
.newsTitle {
  height: 120px;
  width: 100%;
  .el-date {
    height: 100%;
    display: inline-block;
    .date-detail {
      width: 80%;
      height: 80%;
      line-height: 100px;
      text-align: center;
      margin-top: 5%;
      color: #fff;
      background-color: rgb(91, 198, 61);
    }
  }
  .el-desc {
    padding-top: 20px;
  }
}
.news-bottom {
  border-bottom: 1px dashed rgb(235,235,235);
  display: block;
  margin: 7px 0;
  line-height: 30px;
  .item-desc {
    font-size: 12px;
  }
  .item-date{
    display: block;
    float: right;
  }
}
</style>
