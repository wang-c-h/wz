<template>
  <div class="main_page">
    <div class="page_title">
      <!-- 页面标题 + 背景-->
      <div
        class="dashboard_text"
      >
        {{ names }}
        <div class="dashboard_text_subtext">
          集股票行情、股票预测、明日选股为一体的可视化平台
        </div>
      </div>
    </div>
    <div class="dashboard-container">
      <!-- 行情分析可视化 -->
      <el-row type="flex">
        <el-col :span="3"></el-col>
        <el-col :span="4">
          <el-row>
            <div class="tittle_l2">股票行情可视化</div>
          </el-row>
          <el-row style="text-align: center" class="tittle_text1">
            <span class="tittle_text2">实时行情更新,直观分析走势</span>
          </el-row>
        </el-col>
        <el-col :span="5" class="chart-button">
          <el-button style="font-size: '30'" class="ele-button" >
            <span class="ele-text">>>Go Analyzing</span>
          </el-button>
        </el-col>
      </el-row>

      <!-- 明日预测 -->
      <el-row type="flex">
        <el-col :span="6"></el-col>
        <el-col :span="4">
          <el-row>
            <div class="tittle_l2">明日预测</div>
          </el-row>
          <el-row style="text-align: center" class="tittle_text1">
            <span class="tittle_text2">实时行情更新,直观分析走势</span>
          </el-row>
        </el-col>
        <el-col :span="5" class="chart-button">
          <el-button style="font-size: '30'" class="ele-button" >
            <span class="ele-text">>>Go Predict</span>
          </el-button>
        </el-col>
      </el-row>

      <!-- 明日选股 -->
      <el-row type="flex">
        <el-col :span="9"></el-col>
        <el-col :span="4">
          <el-row>
            <div class="tittle_l2">明日选股</div>
          </el-row>
          <el-row style="text-align: center" class="tittle_text1">
            <span class="tittle_text2">实时行情更新,直观分析走势</span>
          </el-row>
        </el-col>
        <el-col :span="5"  class="chart-button">
          <el-button style="font-size: '30'"  class="ele-button" >
            <span class="ele-text" >>>Go Select</span>
          </el-button>
        </el-col>
      </el-row>
    </div>
    <div style="height: 400px"></div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Dashboard",
  data() {
    return {
      names: "股 票 预 测 系 统",
    };
  },
  computed: {
    ...mapGetters(["name"]),
  },
};
</script>

<style lang="scss" scoped>
.main_page {
  
  // opacity: 0.9;
}

.page_title{
  width: 100%;
  background: url("/img/dashboard_background.jpg") center center repeat;
  background-size: cover;
  text-align: center;
  .dashboard_text {
    font-size: 30px;
    line-height: 150px;
    text-align: center;
    padding-bottom: 50px;
    padding-top: 30px;
    // color: #ffff;
  }
    .dashboard_text_subtext {
      font-size: 20px;
      line-height: 50px;
      text-align: center;
      padding-bottom: 30px;
    }
}

.dashboard {
  &-container {
    margin: 30px;
    .tittle_l2 {
      font-size: 25px;
      line-height: 100px;
      text-align: center;
    }
    .tittle_text1 {
      // font-size: 20px;
      text-align: center;
    }
    .tittle_text2 {
      font-size: 18px;
      text-align: center;
    }

    .chart-button {
      line-height: 150px;
      text-align: center;
      .ele-button {
        height: 100%;
        width: 100%;
        font-size: 30px;
        border: 0;
        background-color: transparent;
        .ele-text {
          margin: 5px;
          padding: 5px;
          background: #47c5db86;
          border-radius: 25px;
        }
      }
    }
  }






  // padding: 32px;
  // background-color: rgb(240, 242, 245);
  // position: center;
  // margin: 30px;
  // font-size: 30px;
}
</style>
