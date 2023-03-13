<template>
    <div class="main">
        <el-row class="contentDiv">
            <el-col class="left_select" :span="10">
                <el-row :gutter="4">
                    <el-col :span="20">
                        <el-input v-model="select_stock" placeholder="select stock"></el-input>
                    </el-col>
                    <el-col :span="4"><el-button round type="info" icon="el-icon-circle-plus" class="addButton"></el-button></el-col>
                </el-row>
                <el-row class="selectedStockDiv">
                    <el-table :data="selected_stock" :show-header="false" max-height="400px" >
                        <el-table-column type="selection" width="20px"></el-table-column>
                        <el-table-column prop="code" label='code' align="center"></el-table-column>
                        <el-table-column prop="name" label='name' align="center"></el-table-column>
                    </el-table>
                </el-row>
                <!-- 开始预测 -->
                <el-row class="start_pre">
                    <el-col :span="8"><el-button  type="primary">Select All</el-button></el-col>
                    <el-col :span="8"><el-button  type="danger">Delete Selected</el-button> </el-col>
                    <el-col :span="8"><el-button  type="success">Start Predict</el-button> </el-col>
                </el-row>
            </el-col>

            <el-col class="rignt_select" :span="14">
                <p>建议选股顺序</p>
                <el-row>
                    <el-table :data="suggest_seq" max-height="500px" class="suggest_table" border>
                        <el-table-column prop="name" label="股票名称" align="center"></el-table-column>
                        <el-table-column prop="income" label="预期收益" align="center"></el-table-column>
                    </el-table>
                </el-row>
            </el-col>
        </el-row>
      <div class="show">
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MarketVisualization',
    data() {
        return{
            selected_stock: [{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            },{
                name:'test1',
                code: '000000'
            }],
            suggest_seq: [{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            },{
                name:'test',
                income:'75%'
            }]
        }
    }
  }
  </script>
  
  <style lang="scss" scoped>
  .main{
    font-size: 20px;
    .contentDiv{
        margin: 20px;
        padding: 20px;
        .left_select{
            padding: 15px;
        }
        .rignt_select{
            padding: 15px;
            text-align: center;
        }
    }
  }
  .selectedStockDiv{
    padding-top: 15px;
    padding-right: 45px;
  }
  .addButton{
    margin: auto;
  }
  .suggest_table{
    margin-top: 15px;
  }
  .start_pre{
    margin-top: 10px;
    padding-top: 15px;
  }
</style>
