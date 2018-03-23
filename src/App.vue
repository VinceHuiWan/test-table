<template>
  <div id="app">
    <el-row :gutter="20" type="flex" class="flex-box">
      <el-col :span="24" class="rowHeight">
        <el-form label-width="80px">
          <el-col :span="4">
            <el-form-item label="名称">
              <el-input placeholder="名称" clearable tabindex="1"/>
            </el-form-item>
          </el-col>
        </el-form>
      </el-col>
      <el-col :span="24" class="rowHeight">
        <el-col :span="16"/>
        <el-col :span="8">

          <el-button type="primary" icon="el-icon-delete" class="floatRight buttonMargin">
            清空
          </el-button>
          <el-button type="primary" icon="el-icon-plus" class="floatRight buttonMargin">
            新增
          </el-button>
        </el-col>
      </el-col>
      <div class="tableHeight" ref="colTable">
        <el-col :span="24" class="base-style">
          <el-table
            :data="data"
            class="table-Style"
            element-loading-text="拼命加载中"
            v-bind:height="tableHeight"
            v-bind:max-height="tableHeight"
            empty-text="暂无数据">
            <el-table-column
              label="序号"
              header-align="center"
              type="index"
              :index="1">
            </el-table-column>
            <el-table-column
              prop="Name"
              label="名称"
              header-align="center"
            >
            </el-table-column>
            <el-table-column
              prop="path"
              label="路径"
              header-align="center"
            >
            </el-table-column>
            <el-table-column
              prop="status"
              label="状态"
              header-align="center"
            >
            </el-table-column>
            <el-table-column
              fixed="right"
              label="操作"
              header-align="center"
            >
              <template slot-scope="scope">
                <el-button
                  type="info"
                  size="mini">
                  查看
                </el-button>

              </template>
            </el-table-column>
          </el-table>
        </el-col>
      </div>

      <!--end-->
    </el-row>
  </div>
</template>

<script>

  export default {
    name: "App",
    components: {},
    data() {
      return {
        //主体table高度
        //tableHeight: -1,
        tableHeight: 100,
        data : [
          {
            name: 1,
            path: 2,
            status: 3
          },
          {
            name: 1,
            path: 2,
            status: 3
          },{
            name: 1,
            path: 2,
            status: 3
          },{
            name: 1,
            path: 2,
            status: 3
          },{
            name: 1,
            path: 2,
            status: 3
          },{
            name: 1,
            path: 2,
            status: 3
          },
        ]
      }
    },
    methods: {},
    mounted() {
      this.tableHeight = this.$refs.colTable.offsetHeight;
      console.log(this.tableHeight);
    }
  }
</script>

<style>
  #app {
    width: 100%;
    height: 500px;
    margin: 0;
    padding: 0;
  }

  .el-col {
    padding-top: 5px;
    padding-left: 5px;
    padding-right: 5px;
  }

  .rowHeight {
    height: 6%;
  }

  .tableHeight {
    height: 82%;
  }

  .floatRight {
    float: right;
  }

  .buttonMargin {
    margin-right: 10px
  }

  .base-style {
    width: 100%;
    height: 100%;
  }

  .flex-box {
    flex-direction: column;
    height: 100%;
    width: 100%;
    border: 1px red solid;
  }

  .table-Style {
    width: 100%;
    text-align: center;
  }
</style>
