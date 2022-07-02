<template>
  <div class="app-container">
    <div class="filter-container">
      <el-checkbox-group v-model="formThead">
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

    <el-table :data="tableData" border fit highlight-current-row style="width: 100%">
      <el-table-column prop="name" label="fruitName" width="180" />
      <el-table-column v-for="fruit in formThead" :key="fruit" :label="fruit">
        <template slot-scope="scope">
          {{ scope.row[fruit] }}
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
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
      formThead: ['vue', 'springBoot']
    }
  }
}
</script>
