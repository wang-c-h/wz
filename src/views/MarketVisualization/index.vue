<template>
  <div class="main">
    <!--选项栏 -->
    <div>
      <el-tabs v-model="activeName" class="demo-tabs" @tab-click="handleClick">
        <el-tab-pane label="history" name="first">
          <!-- 大标题 -->
          <div class="title1">历史行情</div>
          <!--  -->
          <el-row class="contentDiv" :gutter="1">
            <el-col class="leftDiv" :span="18">
              <div class="firstImage">
                <div class="option1">option1
                </div>
                <div class="image1">image1
                  <el-image style="width:800px;height:400px" src="/img/test1.jpg" />
                </div>
              </div>
            </el-col>
            <el-col class="rightDiv" :span="5">
              <el-input v-model="stock_select_data" placeholder="Select Stock" ></el-input>
              <p style="text-align: center; margin: 10px;">股票详情</p>
              <el-table :show-header="false" :data="stockinfo" border class="stock_table">
                <el-table-column prop="name" label="name" align="center"/>
                <el-table-column prop="datass" label="datass" align="center"/>
              </el-table>
            </el-col>
          </el-row>
        </el-tab-pane>
        <el-tab-pane label="now" name="second">
          <!-- 大标题 -->
          <div class="title1">实时行情</div>
          <!--  -->
          <el-row class="contentDiv" :gutter="1">
            <el-col class="leftDiv" :span="18">
              <div class="firstImage">
                <div class="option1">option1
                </div>
                <div class="image1">image1
                  <el-image style="width:800px;height:400px" src="/img/test1.jpg" />
                </div>
              </div>
            </el-col>
            <el-col class="rightDiv" :span="5">
              <el-input v-model="stock_select_data" placeholder="Select Stock"></el-input>
              <p style="text-align: center; margin: 10px;">股票详情</p>
              <el-table :show-header="false" :data="stockinfo_now" border  class="stock_table">
                <el-table-column prop="name" label="name" align="center"/>
                <el-table-column prop="datass" label="datass" align="center"/>
              </el-table>
            </el-col>
          </el-row>
        </el-tab-pane>
      </el-tabs>
      <!-- <el-row>
        <el-col :span="2">
          <el-button>历史行情</el-button>
        </el-col>
        <el-col :span="2">
          <el-button>实时行情</el-button>
        </el-col>
      </el-row> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'MarketVisualization',
  data() {
    return {
      activeName: 'first',
      stockinfo: [{
        name: '股票名称',
        datass: 'test'
      }, {
        name: '股票代码',
        datass: 'test'
      }, {
        name: '所属行业',
        datass: 'test'
      }, {
        name: '市盈率',
        datass: 'test'
      }, {
        name: '每股收益',
        datass: 'test'
      }, {
        name: '市净值',
        datass: 'test'
      }, {
        name: '上市日期',
        datass: 'test'
      }],
      stock_select_data: '',
      stockinfo_now: [{
        name: '开盘价',
        datass: 'test'
      }, {
        name: '收盘价',
        datass: 'test'
      }, {
        name: '最高价',
        datass: 'test'
      }, {
        name: '最低价',
        datass: 'test'
      }, {
        name: '成交量',
        datass: 'test'
      }, {
        name: '成交额',
        datass: 'test'
      }, {
        name: '均价',
        datass: 'test'
      }]
    }
  },
  method: {
    handleClick() {
      console.log('change tabs')
    }
  }
}
</script>

<style lang="scss" scoped>
.main {
  font-size: 20px;

  .demo-tabs {
    padding: 20px;
  }
}
.stock_table{
  text-align: center;
}

.title1{
  text-align: center;
  font-size: 35px;
}
</style>
