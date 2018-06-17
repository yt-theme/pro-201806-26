<template>
  <div class="table-container">
    <el-table
      :data="tableData"
      style="width:100%">
      <el-table-column
        prop="owner"
        label="户主">
      </el-table-column>
      <el-table-column
        prop="position"
        label="房址">
      </el-table-column>
      <el-table-column
        prop="fee"
        label="欠费(元)">
      </el-table-column>
      <el-table-column
        prop="timer"
        label="欠费时长">
      </el-table-column>
    </el-table>
  </div>
</template>
<script>
export default {
  name: 'DataCenterPieCircle',
  data () {
    return {
      tableData: [
        {
          owner: '高思远',
          position: '1-1-101',
          fee: '3786.00',
          timer: '2年8个月'
        },
        {
          owner: '高思远',
          position: '1-1-101',
          fee: '3786.00',
          timer: '2年8个月'
        },
        {
          owner: '高思远',
          position: '1-1-101',
          fee: '3786.00',
          timer: '2年8个月'
        }
      ]
    }
  }
}
</script>
<style scope>
  .table-container {
    width: 30.859375%;
    height: 330px;
  }
</style>
