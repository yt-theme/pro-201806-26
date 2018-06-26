<template>
  <div class="EquipmentBody-menjin-listItem-container">
    <div class="menjin-listItem-title">
      <div class="listItem-title-left">
        <div class="listDot"></div>
        <div class="listText">{{listItemTitle}}</div>
      </div>
      <div class="listLine"></div>
    </div>
    <div class="menjin-listItem-wrap">
      <EquipmentBodyMenJinListItemSectoin></EquipmentBodyMenJinListItemSectoin>
      <EquipmentBodyMenJinListItemSectoin></EquipmentBodyMenJinListItemSectoin>
      <EquipmentBodyMenJinListItemSectoin></EquipmentBodyMenJinListItemSectoin>
    </div>
  </div>
</template>
<script>
import EquipmentBodyMenJinListItemSectoin from './EquipmentBody_menjin_ListItemSection.vue'
export default {
  name: 'EquipmentBodyMenJinListItem',
  components: {
    EquipmentBodyMenJinListItemSectoin
  },
  data () {
    return {
      listItemTitle: '门禁设备'
    }
  }
}
</script>
<style scoped>
  .EquipmentBody-menjin-listItem-container {

  }
  .listDot {
    width: 11px;
    height: 11px;
    background-color: #55b2ff;
    border-radius: 100%;
  }
  .menjin-listItem-title {
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }
  .listItem-title-left {
    width: 16.07%;
    max-width: 90px;
    display: flex;
    justify-content:space-between;
    align-items: center;
  }
  .listText {
    color: #55b2ff;
  }
  .listLine {
    width: 100%;
    border-bottom: 1px solid #e6e6e6;
    margin-left: 16px;
  }
  .menjin-listItem-wrap {
    display: flex;
    flex-wrap: wrap;
  }
</style>
