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
                <div class="option1"></div>
                <div class="image1">
                  <el-image
                    style="width: 1200px; height: 600px"
                    src="/img/history.png"
                  />
                </div>
              </div>
            </el-col>
            <el-col class="rightDiv" :span="5">
                <el-select class="select_stock_input_div"
                v-model="stock_select_data"
                placeholder="Select Stock"
              ></el-select>
              <el-form ref="form" :model="stock_form" label-width="80px">
                <el-form-item label="选择时间" class="el_form_label_div">
                  <el-col :span="18">
                    <el-date-picker class="el-date-picker_div"
                      type="date"
                      placeholder="开始日期"
                      v-model="stock_form.date1"
                      style="width: 100%"
                    ></el-date-picker>
                  </el-col>
                  <el-col class="line" :span="2">--</el-col>
                  <el-col :span="18">
                    <el-date-picker class="el-date-picker_div"
                      type="date"
                      placeholder="截止日期"
                      v-model="stock_form.date2"
                      style="width: 100%"
                    ></el-date-picker>
                  </el-col>
                </el-form-item>
              </el-form>
              <p style="text-align: center; margin: 10px">股票详情</p>
              <el-table
                :show-header="false"
                :data="stockinfo"
                border
                class="stock_table"
              >
                <el-table-column prop="name" label="name" align="center" />
                <el-table-column prop="datass" label="datass" align="center" />
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
                <div class="option1"></div>
                <div class="image1">
                  <el-image
                    style="width: 1200px; height: 600px"
                    src="/img/history.png"
                  />
                </div>
              </div>
            </el-col>
            <el-col class="rightDiv" :span="5">
              <el-input class="select_stock_input_div"
                v-model="stock_select_data"
                placeholder="Select Stock"
              ></el-input>
              <el-form ref="form" :model="stock_form" label-width="80px">
                <el-form-item label="选择时间" class="el_form_label_div">
                  <el-col :span="18">
                    <el-date-picker class="el-date-picker_div"
                      type="date"
                      placeholder="开始日期"
                      v-model="stock_form.date1"
                      style="width: 100%"
                    ></el-date-picker>
                  </el-col>
                  <el-col class="line" :span="2">--</el-col>
                  <el-col :span="18">
                    <el-date-picker class="el-date-picker_div"
                      type="date"
                      placeholder="截止日期"
                      v-model="stock_form.date2"
                      style="width: 100%"
                    ></el-date-picker>
                  </el-col>
                </el-form-item>
              </el-form>
              <p style="text-align: center; margin: 10px">股票详情</p>
              <el-table
                :show-header="false"
                :data="stockinfo_now"
                border
                class="stock_table"
              >
                <el-table-column prop="name" label="name" align="center" />
                <el-table-column prop="datass" label="datass" align="center" />
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
  name: "MarketVisualization",
  data() {
    return {
      activeName: "first",
      stockinfo: [
        {
          name: "股票名称",
          datass: "伊力特",
        },
        {
          name: "股票代码",
          datass: "600197.SH",
        },
        {
          name: "所属行业",
          datass: "白酒",
        },
        {
          name: "市盈率",
          datass: "70.17",
        },
        {
          name: "每股收益",
          datass: "0.3",
        },
        {
          name: "总市值",
          datass: "130.73亿",
        },
        {
          name: "上市日期",
          datass: "1999-09-16",
        },
      ],
      stock_select_data: "600197.SH  伊力特",
      stockinfo_now: [
        {
          name: "开盘价",
          datass: "test",
        },
        {
          name: "收盘价",
          datass: "test",
        },
        {
          name: "最高价",
          datass: "test",
        },
        {
          name: "最低价",
          datass: "test",
        },
        {
          name: "成交量",
          datass: "test",
        },
        {
          name: "成交额",
          datass: "test",
        },
        {
          name: "均价",
          datass: "test",
        },
      ],
      stock_form: {
        name: "",
        region: "",
        date1: "2022-5-5",
        date2: "2022-12-30",
        delivery: false,
        type: [],
        resource: "",
        desc: "",
      },
    };
  },
  method: {
    handleClick() {
      console.log("change tabs");
    },
  },
};
</script>

<style lang="scss" scoped>
.main {
  font-size: 20px;

  .demo-tabs {
    padding: 20px;
  }
}
.stock_table {
  text-align: center;
}

.title1 {
  text-align: center;
  font-size: 35px;
}
.image1 {
  margin-top: 20px;
}
.select_stock_input_div{
  margin: 10px;
  width: 100%;
}
.el-date-picker_div{
  margin: 5px;
}
.line{
  margin: 5px;
  font-size: 20px;
}
.el_form_label_div{
  margin: 5px;
  font-size: 20px;
}
</style>
