<template>
  <div class="app-container">
    <div class="filter-container">
      <el-checkbox-group v-model="checkboxVal">
        <el-checkbox label="vue">
          vue
        </el-checkbox>
        <el-checkbox label="springBoot">
          springBoot
        </el-checkbox>
        <el-checkbox label="eslint">
          eslint
        </el-checkbox>
      </el-checkbox-group>
    </div>

    <el-table :key="key" :data="tableData" border fit highlight-current-row style="width: 100%">
      <el-table-column prop="name" label="className" width="180" />
      <el-table-column v-for="fruit in formThead" :key="fruit" :label="fruit">
        <template slot-scope="scope">
          {{ scope.row[fruit] }}
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
const defaultFormThead = ['vue', 'springBoot']

export default {
  data() {
    return {
      tableData: [
        {
          name: 'class-1',
          vue: 'vue-10',
          springBoot: 'springBoot-10',
          eslint: 'eslint-10'
        },
        {
          name: 'class-2',
          vue: 'vue-20',
          springBoot: 'springBoot-20',
          eslint: 'eslint-20'
        }
      ],
      key: 1, // table key
      formTheadOptions: ['vue', 'springBoot', 'eslint'],
      checkboxVal: defaultFormThead, // checkboxVal
      formThead: defaultFormThead // 默认表头 Default header
    }
  },
  watch: {
    checkboxVal(valArr) {
      this.formThead = this.formTheadOptions.filter(i => valArr.indexOf(i) >= 0)
      this.key = this.key + 1// 为了保证table 每次都会重渲
    }
  }
}
</script>
