<template>
  <div class="dashboard-container">
    <!-- 页面标题 + 背景-->
    <div class="dashboard-text" style="background:#fff;padding:16px 16px 0;margin-bottom:32px;">{{ names }}
      <div class="dashboard-text-subtext"> 集股票行情、股票预测、明日选股为一体的可视化平台</div>
    </div>
    <!-- 行情分析可视化 -->
    <el-row >
      <el-col type="flex" :span="6">
        <el-row>
          <div class="chart-wrapper">
              股票行情可视化
          </div>
        </el-row>
        <el-row style="text-align: center;">
          <el-col style="text-align: center;">
            实时行情更新,直观分析走势
          </el-col>
        </el-row>
      </el-col>
      <el-col :span="6" > </el-col>
      <el-col :span="6" class="chart-button">
              <el-button :size="large" style="font-size:'30'" class="ele-button">
                >>Go Analyzing
              </el-button>
      </el-col>
    </el-row>

    <!-- 明日预测 -->
    <el-row type="flex" justify="center">
      <el-col :span="6">
        <el-row>
          <div class="chart-wrapper">
            明日预测
          </div>
        </el-row>
        <el-row style="text-align: center;">
          <el-col style="text-align: center;">
            实时行情更新,直观分析走势
          </el-col>
        </el-row>
      </el-col>
      <el-col :span="6" > </el-col>
      <el-col :span="6" class="chart-button">
              <el-button :size="large" style="font-size:'30'" class="ele-button">
                >>Go Analyzing
              </el-button>
      </el-col>
    </el-row>

    <!-- 明日选股 -->
    <el-row type="flex" justify="end">
      <el-col :span="6">
        <el-row>
          <div class="chart-wrapper">
            明日选股
          </div>
        </el-row>
        <el-row style="text-align: center;">
          <el-col style="text-align: center;">
            实时行情更新,直观分析走势
          </el-col>
        </el-row>
      </el-col>
      <el-col :span="6" > </el-col>
      <el-col :span="6" class="chart-button">
              <el-button :size="large" style="font-size:'30'" class="ele-button">
                >>Go Analyzing
              </el-button>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  data() {
    return {
      names: '股票预测系统'
    }
  },
  computed: {
    ...mapGetters([
      'name'
    ])
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
    .chart-wrapper {
    font-size: 20px;
    line-height: 100px;
    text-align: center;
    // background: #fff;
    // padding: 16px 16px 0;
    // margin-bottom: 32px;
    // font-size: 30px;
  }
  .chart-button {
    line-height: 150px;
    text-align: center;
    // margin-left: 0;
    // margin-bottom: 0;
    // background: #fff;
    // padding: 16px 16px 0;
    // margin-bottom: 32px;
    // font-size: 30px;
    .ele-button{
      height: 100%;
      width: 100%;
      font-size: 30px;
      // position: relative;
      // bottom: 10%;

    }
  }
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
    text-align: center;
    .dashboard-text-subtext {
      font-size: 15px;
      line-height: 26px;
      text-align: center;
    }
  }

  // padding: 32px;
  // background-color: rgb(240, 242, 245);
  // position: center;
  // margin: 30px;
  // font-size: 30px;
}
</style>
