<template>
  <div class="cron-main">
    <div class="cron-setting">
      <el-tabs v-model="activeName">
        <el-tab-pane label="秒" name="first">
          <SecondTab/>
        </el-tab-pane>
        <el-tab-pane label="分" name="second">配置管理</el-tab-pane>
        <el-tab-pane label="时" name="third">角色管理</el-tab-pane>
        <el-tab-pane label="日" name="fourth">定时任务补偿</el-tab-pane>
        <el-tab-pane label="月" name="fifth">定时任务补偿</el-tab-pane>
        <el-tab-pane label="周" name="sixth">定时任务补偿</el-tab-pane>
        <el-tab-pane label="年" name="seventh">定时任务补偿</el-tab-pane>
      </el-tabs>
    </div>
    <div class="divider">
      <el-divider content-position="left" direction="vertical">11</el-divider>
    </div>
    <div class="cron-preview">
      <el-table
          :header-cell-style="{background:'#F3F4F7',color:'#555'}"
          :data="tableData"
          border
          style="width: 100%">
        <el-table-column
            width="60"
            prop="period"
            label="时段">
        </el-table-column>
        <el-table-column

            prop="value"
            label="时段值">
        </el-table-column>
      </el-table>
      <div class="execute-preview-content" style="margin-bottom: 10px">
        <label class="preview-left">执行时间：</label>
        <el-date-picker
            class="preview-right"
            value-format="yyyy-MM-dd HH:mm:ss"
            size="mini"
            v-model="value1"
            type="datetime"
            placeholder="选择日期时间">
        </el-date-picker>
      </div>
      <div class="execute-preview-content">
        <label class="preview-left">执行预览：</label>
        <el-input
            class="preview-right"
            readonly
            type="textarea"
            :rows="4"
            placeholder="请输入内容"
            v-model="textarea">
        </el-input>
      </div>

    </div>

  </div>
</template>
<script>
import SecondTab from '@/components/SecondTab';
import moment from 'moment'


export default {
  name: "Crontab",
  components: {
    SecondTab
  },
  data() {
    return {
      activeName: 'first',
      tableData: [
        {
          period: '秒',
          value: '*',
        },
        {
          period: '分',
          value: '*',
        },
        {
          period: '时',
          value: '*',
        },
        {
          period: '日',
          value: '*',
        },
        {
          period: '月',
          value: '*',
        },
        {
          period: '周',
          value: '*',
        },
        {
          period: '年',
          value: '*',
        }
      ],
      value1: moment().format('YYYY-MM-DD HH:mm:ss'),
      textarea: ''
    }
  }
}
</script>

<style scoped>
.cron-main {
  margin: 50px auto;
  width: 750px;
  border: 1px solid gray;
  border-radius: 5px;
  padding: 15px;
  display: flex;
  justify-content: space-between;
}

.cron-setting {
  flex-basis: 60%;
  width: 60%;
}

.cron-preview {
  flex-basis: 40%;
  width: 40%;
}

/deep/ .el-divider--vertical {
  height: 100%;
  width: 1.5px;
}

.execute-preview-content {
  display: flex;
  margin: 5px 0;
  justify-content: flex-start;
}

.preview-left {
  font-size: 14px;
  font-weight: bold;
  color: #9d9da1;
  flex-basis: 80px;
  flex-grow: 0;
  display: flex;
  align-items: center;
}

.preview-right {
  flex-basis: 100px;
  flex-grow: 1;
}

.time-content {
  flex-basis: 100px;
  flex-grow: 1;
}


</style>