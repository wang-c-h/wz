<template>
  <div class="main">
    <el-row class="contentDiv">
      <el-col class="left_select" :span="6">
        <el-row class="tittle_text">单股票预测</el-row>
        <el-row :gutter="4" class="select_stock_div">
          <el-col :span="18">
            <el-select v-model="select_stock_singnl" placeholder="select stock" style="width:100%"></el-select>
          </el-col>
          <el-col :span="4"><el-button round type="success" class="addButton">Predict</el-button></el-col>
        </el-row>
        <el-row class="tittle_text">多股票预测</el-row>
        <el-row :gutter="4" class="select_stock_div">
          <el-col :span="18">
            <el-select v-model="select_stock_multi" placeholder="select stock" multiple style="width:100%"></el-select>
          </el-col>
          <el-col :span="4"><el-button round type="success" class="addButton">Predict</el-button></el-col>
        </el-row>
        <el-row class="tittle_text">自选股预测</el-row>
        <el-row :gutter="4" class="select_stock_div">
          <el-col :span="18">
            <el-select v-model="select_stock_self" placeholder="select stock" multiple style="width:100%"></el-select>
          </el-col>
          <el-col :span="4"><el-button round type="success" class="addButton">Predict</el-button></el-col>
        </el-row>
        <el-row class="selectedStockDiv">
          <el-table :data="selected_stock" :show-header="false" max-height="400px">
            <el-table-column type="selection" width="20px"></el-table-column>
            <el-table-column prop="code" label='code' align="center"></el-table-column>
            <el-table-column prop="name" label='name' align="center"></el-table-column>
          </el-table>
        </el-row>
        <!-- 开始预测 -->
        <el-row class="start_pre">
          <el-col :span="12"><el-button type="primary">Select All</el-button></el-col>
          <el-col :span="12"><el-button type="danger">Delete Selected</el-button> </el-col>
          <!-- <el-col :span="8"><el-button  type="success">Start Predict</el-button> </el-col> -->
        </el-row>
      </el-col>
      <el-col class="rignt_select" :span="18">
        <p class="tittle_text2">预测走势</p>
        <!-- <el-row>
          <el-table :data="suggest_seq" max-height="500px" class="suggest_table" border>
            <el-table-column prop="name" label="股票名称" align="center"></el-table-column>
            <el-table-column prop="income" label="预期收益" align="center"></el-table-column>
          </el-table>
        </el-row> -->
        <el-row max-height="1000px">
          <div class="chart-wrapper">
            <Candlestick></Candlestick>
          </div>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import Candlestick from './component/Candlestick'

export default {
  name: 'Forecast',
  components: { Candlestick },
  data() {
    return {
      select_stock_singnl: [{
        name: '伊力特',
        code: '600197.SH'
      }],
      select_stock_multi: [],
      select_stock_self: [],
      selected_stock: [{
        name: '伊力特',
        code: '600197.SH'
      }, {
        name: '水井坊',
        code: '600779.SH'
      }, {
        name: '顺鑫农业',
        code: '000860.SZ'
      }, {
        name: '五粮液',
        code: '000858.SZ'
      }, {
        name: '洋河股份',
        code: '002304.SZ'
      }, {
        name: '贵州茅台',
        code: '600519.SH'
      }, {
        name: '泸州老窖',
        code: '000568.SZ'
      }, {
        name: '古井贡酒',
        code: '000596.SZ'
      }, {
        name: '酒鬼酒',
        code: '000799.SZ'
      }, {
        name: '山西汾酒',
        code: '600809.SH'
      }]
    }
  }
}
</script>

<style lang="scss" scoped>
.main {
  font-size: 20px;

  .contentDiv {
    margin: 25px;
    margin-right: 10px;
    padding: 10px;
  }

  .start_pre {
    text-align: center;
  }

  .tittle_text {
    margin-top: 5px;
    margin-bottom: 10px;
    text-align: center;
    right: 10%
  }

  .tittle_text2 {
    margin-top: 5px;
    margin-bottom: 15px;
    text-align: center;
  }

  .select_stock_div {
    margin-top: 5px;
    margin-bottom: 5px;
  }

  .selectedStockDiv {
    margin-top: 35px;
  }

  .chart-wrapper {
    padding: 8px;
    text-align: center;
  }

  .rignt_select {
    text-align: center;
  }
}
</style>
