<template>
  <div>
    <!-- 學生詳情彈出框元件 -->
    <student-details-dialog
      :visible.sync="showDetails"
      :student="currentStudent"
      @close-dialog="showDetails = false"
    ></student-details-dialog>
<!-- 學生列表表格 -->
  <!-- 主表格 -->
<el-table :data="students" border style="width: 100%">
  <!-- 循環渲染表格列 -->
      <el-table-column
        v-for="(column, index) in mainTableColumns"
        :key="index"
        :prop="column.prop"
        :label="column.label"
      ></el-table-column>
      <!-- 操作列，用於查看學生詳情 -->
      <el-table-column fixed="right" label="操作" width="100">
        <template slot-scope="scope">
          <el-button @click="showDetails = true; currentStudent = scope.row">
            查看學生詳情
          </el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
// 導入學生數據和學生詳情彈出框元件
import studentsData from "../assets/json/students.json";
import StudentDetailsDialog from "./StudentDetailsDialog.vue";

export default {
  components: {
    StudentDetailsDialog,
  },
  data() {
    return {
      // 控制學生詳情彈出框的顯示與隱藏
      showDetails: false,
      // 學生數據列表
      students: studentsData,
      // 當前選中的學生
      currentStudent: {},
      // 主表格的列配置
      mainTableColumns: [
        { prop: "name", label: "姓名" },
        { prop: "birthday", label: "生日" },
        { prop: "gender", label: "性別" },
      ],
    };
  },
};
</script>
