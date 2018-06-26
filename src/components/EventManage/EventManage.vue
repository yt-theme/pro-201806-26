<template>
  <div class="EventManage-container">
    <div class="EventManage-head">
        <el-select placeholder="--栋--" class="EventManage-build">
          <el-option v-for="i in downBuildData" :label="i.buildname" :value=i.id></el-option>
        </el-select>
        <el-select placeholder="--单元--" class="EventManage-unit">
          <el-option v-for="i in downUnitData" :label="i.unitname" :value=i.id></el-option>
        </el-select>
        <el-select placeholder="--门牌号--" class="EventManage-number">
          <el-option v-for="i in downNumberData" :label="i.number" :value=i.id></el-option>
        </el-select>
        <el-select placeholder="--事件类型--" class="EventManage-type">
          <el-option v-for="i in downNumberData" :label="i.number" :value=i.id></el-option>
        </el-select>
        <el-date-picker
          v-model="selectedDate"
          type="daterange"
          range-separator="至"
          start-placeholder="开始日期"
          end-placeholder="结束日期">
        </el-date-picker>
        <el-button type="primary" icon="el-icon-search"></el-button>
        <el-button type="danger" icon="el-icon-refresh"></el-button>
    </div>
    <div class="EventManage-table">
      <el-table
        :data="tableData"
        border
        style="width: 100%">
      <el-table-column
        prop="level"
        label="业主星级"
        width="180">
      </el-table-column>
      <el-table-column
        prop="estate_address"
        label="房产地址"
        width="180">
      </el-table-column>
      <el-table-column
        prop="contacts"
        label="联系人">
      </el-table-column>
      <el-table-column
        prop="contact_number"
        label="联系电话">
      </el-table-column>
      <el-table-column
        prop="launch_time"
        label="发起时间">
      </el-table-column>
      <el-table-column
        prop="event_type"
        label="事件类型">
      </el-table-column>
      <el-table-column
        prop="event_describe"
        label="事件描述">
      </el-table-column>
      <el-table-column
        prop="event_photo"
        label="事件图片">
      </el-table-column>
      <el-table-column
        prop="event_state"
        label="事件状态">
      </el-table-column>
      <el-table-column
        fixed="right"
        label="操作"
        width="100">
        <template slot-scope="scope">
          <el-button @click="handleClick(scope.row)" type="text" size="small">回访</el-button>
          <el-button type="text" size="small">分配</el-button>
          <el-button type="text" size="small">完成</el-button>
        </template>
      </el-table-column>
    </el-table>
    </div>
  </div>
</template>
<script>
export default {
  name: 'EventManage',
  data () {
    return {
      downBuildData: [
        {buildname:"01",id:1},
        {buildname:"02",id:2}
      ],
      downUnitData: [
        {unitname:"001",id:1},
        {unitname:"002",id:2}
      ],
      downNumberData: [
        {number:"0001",id:1},
        {number:"0002",id:2}
      ],
      tableData: [
        {
          "level":5,
          "estate_address": "1-1-101",
          "contacts": "高思远",
          "contact_number": "18332567500",
          "launch_time": "2018-06-19",
          "event_describe": "窗台玻璃炸裂",
          "event_state": "待分配",
          "event_type": "房屋主体"
        },
        {
          "level":3,
          "estate_address": "1-2-101",
          "contacts": "罗新新",
          "contact_number": "18713548785",
          "launch_time": "2018-06-19",
          "event_describe": "楼道灯坏了",
          "event_state": "待分配",
          "event_type": "公共照明"
        },
        {
          "level":2,
          "estate_address": "2-2-301",
          "contacts": "张素娇",
          "contact_number": "13131587548",
          "launch_time": "2018-06-18",
          "event_describe": "卧室侧墙有裂缝",
          "event_state": "处理中",
          "event_type": "房屋主体"
        },
        {
          "level":3,
          "estate_address": "4-1-602",
          "contacts": "周扬",
          "contact_number": "13131354879",
          "launch_time": "2018-06-18",
          "event_describe": "车位被不明车辆占位",
          "event_state": "处理中",
          "event_type": "乱停乱放"
        },
        {
          "level":3,
          "estate_address": "1-1-102",
          "contacts": "张亚康",
          "contact_number": "18733507870",
          "launch_time": "2018-06-15",
          "event_describe": "水路问题",
          "event_state": "已完成",
          "event_type": "家庭水路"
        },
        {
          "event_id": 246,
          "level":1,
          "estate_address": "6-1-102",
          "contacts": "张文凯",
          "contact_number": "13144444441",
          "launch_time": "2018-06-15",
          "event_describe": "客厅墙上有裂缝",
          "event_state": "已完成",
          "event_type": "房屋主体"
        },
        {
          "level":2,
          "estate_address": "1-1-103",
          "contacts": "秦波",
          "contact_number": "18733507870",
          "launch_time": "2018-06-14",
          "event_describe": "车乱停",
          "event_state": "已完成",
          "event_type": "乱停乱放"
        },
        {
          "level":3,
          "estate_address": "4-2-105",
          "contacts": "张楚生",
          "contact_number": "18733507870",
          "launch_time": "2018-06-14",
          "event_describe": "路灯坏了",
          "event_state": "已完成",
          "event_type": "公共照明"
        },
        {
          "level":5,
          "estate_address": "12-1-103",
          "contacts": "张艺馨",
          "contact_number": "18733507870",
          "launch_time": "2018-06-13",
          "event_describe": "电线折了",
          "event_state": "已完成",
          "event_type": "家庭电路"
        },
        {
          "level":3,
          "estate_address": "10-2-202",
          "contacts": "周正要",
          "contact_number": "18733507870",
          "launch_time": "2018-06-11",
          "event_describe": "隔壁大声的吵闹",
          "event_state": "已完成",
          "event_type": "噪声干扰"
        },
        {
          "level":4,
          "estate_address": "20-3-105",
          "contacts": "冯祥波",
          "contact_number": "18731507870",
          "launch_time": "2018-06-08",
          "event_describe": "车位被别人占了",
          "event_state": "已完成",
          "event_type": "乱停乱放"
        },
        {
          "level":5,
          "estate_address": "3-2-301",
          "contacts": "赵文君",
          "contact_number": "18733507873",
          "launch_time": "2018-05-30",
          "event_describe": "车位被人占了",
          "event_state": "已完成",
          "event_type": "乱停乱放"
        },
        {
          "level":4,
          "estate_address": "13-1-101",
          "contacts": "赵昆丽",
          "contact_number": "13130565214",
          "launch_time": "2018-05-20",
          "event_describe": "房屋有裂缝",
          "event_state": "未接受",
          "event_type": "房屋主体"
        },
        {
          "level":4,
          "estate_address": "22-2-101",
          "contacts": "张博轩",
          "contact_number": "13257489852",
          "launch_time": "2018-05-19",
          "event_describe": "水管坏了",
          "event_state": "处理中",
          "event_type": "家庭水路"
        }
      ],
      selectedBuild: '',
      selectedUnit: '',
      selectedNumber: '',
      selectedDate: ''
    }
  }
}
</script>
<style scoped>
  .EventManage-container {

  }
  .EventManage-table {
    height: 81vh;
    overflow: auto;
  }
</style>
