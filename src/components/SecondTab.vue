<template>
  <div class="second-settings">
    <div class="select-item">
      <el-radio-group v-model="type">
        <el-radio label="TYPE_EVERY" class="choice">每秒</el-radio>
      </el-radio-group>
    </div>
    <div class="select-item">
      <el-radio label="TYPE_EVERY" class="choice">区间</el-radio>
      从
      <el-input-number v-model="num" controls-position="right" size="mini" class="w60" :disabled="true"/>
      秒
      至
      <el-input-number v-model="num" controls-position="right" size="mini" class="w60" :disabled="true"/>
      秒
    </div>
    <div class="select-item">
      <el-radio label="TYPE_EVERY" class="choice">循环</el-radio>
      从
      <el-input-number v-model="num" controls-position="right" size="mini" class="w60" :disabled="true"/>
      秒开始，
      间隔
      <el-input-number v-model="num" controls-position="right" size="mini" class="w60" :disabled="true"/>
      秒
    </div>
    <div class="select-item">
      <el-radio label="TYPE_EVERY" class="choice">指定</el-radio>
      <div class="time-item-list">
        <el-checkbox-group v-model="checkList">
          <el-checkbox v-for="(item,index) in 60" :key="`key-${item-1}`" :label="item-1"
                       class="time-item">
            {{ item - 1 }}
          </el-checkbox>
        </el-checkbox-group>
      </div>
    </div>


  </div>

</template>

<script>
export default {
  name: "SecondTab",
  data() {
    return {
      type: '',
      num: '',
      checkList: [],
      aa: []
    }
  }
}
</script>

<style scoped>
/deep/ .el-checkbox__label{
  font-size: 12px !important;
}

.second-settings {
  text-align: left;
  padding: 10px;
}

.select-item {
  margin: 20px 0;
  font-size: 12px;
}

.choice {
  padding: 5px 8px;
  margin-right: 10px;
}

.w60 {
  width: 80px;
  margin: 0 4px;
}

.time-item-list {
  margin: 10px 20px;
}

.time-item {
  padding: 1px 3px;
  width: 26px;
}

</style>