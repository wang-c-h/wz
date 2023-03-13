<template>
  <div class="main">
    <el-row class="contentDiv">
      <el-col class="left_select" :span="10">
        <el-row :gutter="4">
          <el-col :span="20">
            <el-input
              v-model="select_stock"
              placeholder="select stock"
            ></el-input>
          </el-col>
          <el-col :span="4"
            ><el-button
              round
              type="info"
              icon="el-icon-circle-plus"
              class="addButton"
            ></el-button
          ></el-col>
        </el-row>
        <el-row class="selectedStockDiv">
          <el-table
            :data="selected_stock"
            :show-header="false"
            max-height="400px"
          >
            <el-table-column type="selection" width="20px"></el-table-column>
            <el-table-column
              prop="code"
              label="code"
              align="center"
            ></el-table-column>
            <el-table-column
              prop="name"
              label="name"
              align="center"
            ></el-table-column>
          </el-table>
        </el-row>
        <!-- 开始预测 -->
        <el-row class="start_pre">
          <el-col
            :span="8"
            ><el-button type="primary">Select All</el-button></el-col
          >
          <el-col
            :span="8"
            ><el-button type="danger">Delete Selected</el-button>
          </el-col>
          <el-col
            :span="8"
            ><el-button type="success">Start Predict</el-button>
          </el-col>
        </el-row>
      </el-col>

      <el-col class="rignt_select" :span="14">
        <p>建议选股顺序</p>
        <el-row>
          <el-table
            :data="suggest_seq"
            max-height="500px"
            class="suggest_table"
            border
            :row-class-name="tableRowClassName"
          >
            <el-table-column
              prop="name"
              label="股票名称"
              align="center"
            ></el-table-column>
            <el-table-column
              prop="income"
              label="预测涨跌幅"
              align="center"
            ></el-table-column>
          </el-table>
        </el-row>
      </el-col>
    </el-row>
    <div class="show"></div>
  </div>
</template>

<script>
export default {
  name: 'MarketVisualization',
  data() {
    return {
      select_stock: [],
      selected_stock_old: [
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
        {
          name: 'test1',
          code: '000000'
        },
      ],
      selected_stock: [
        { name: "川投能源", code: "600674.SH" },
        { name: "川能动力", code: "000155.SZ" },
        { name: "长江电力", code: "600900.SH" },
        { name: "申能股份", code: "600642.SH" },
        { name: "华银电万", code: "600744.SH" },
        { name: "天富能源", code: "600509.SH" },
        { name: "华电能源", code: "600726.SH" },
        { name: "东旭蓝天", code: "000040.SZ" },
        { name: "大唐发电", code: "601991.SH" },
        { name: "金山股份", code: "600396.SH" },
      ],
      suggest_seq: [
        { name: "华电能源", income: "+8.47%" },
        { name: "川投能源", income: "+6.71%" },
        { name: "川能动力", income: "+5.27%" },
        { name: "长江电力", income: "+3.76%" },
        { name: "申能股份", income: "+1.74%" },
        { name: "天富能源", income: "+1.73%" },
        { name: "金山股份", income: "+1.24%" },
        { name: "华银电万", income: "-0.66%" },
        { name: "大唐发电", income: "-1.02%" },
        { name: "东旭蓝天", income: "-3.14%" },
      ],
    };
  },
  methods: {
    tableRowClassName({ row }) {
      var income = Number(row.income.split("%")[0]);
    //   console.log(income);
      if (income <= -3) {
        // console.log("waring");
        return "warning-row";
      } else if (income >= 5) {
        // console.log("success");
        return "success-row";
      }
      return "";
    },
  },
};
</script>

  <style lang="scss" scoped>
.main {
  font-size: 20px;
  .contentDiv {
    margin: 20px;
    padding: 20px;
    .left_select {
      padding: 15px;
    }
    .rignt_select {
      padding: 15px;
      text-align: center;
    }
  }
}
.selectedStockDiv {
  padding-top: 15px;
  padding-right: 45px;
}
.addButton {
  margin: auto;
}
.suggest_table {
  margin-top: 15px;
}
.start_pre {
  margin-top: 10px;
  padding-top: 15px;
}
.suggest_table .warning-row {
  background: rgb(233, 144, 11);
}

.suggest_table .success-row {
  background: #59f803;
}
</style>
