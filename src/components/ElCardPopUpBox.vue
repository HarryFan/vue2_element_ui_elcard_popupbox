<template>
  <div>
    <el-button @click="showDetails = true">學生詳情</el-button>
    <el-dialog
      :visible.sync="showDetails"
      title="學生詳情"
      width="30%"
    >
      <el-card>
        <el-table :data="students" border stripe>
          <el-table-column prop="name" label="姓名"></el-table-column>
          <el-table-column prop="birthday" label="生日"></el-table-column>
          <el-table-column prop="gender" label="性別"></el-table-column>
          <el-table-column prop="grade" label="年級"></el-table-column>
          <el-table-column prop="phone" label="手機號碼"></el-table-column>
        </el-table>
      </el-card>
      <span slot="footer" class="dialog-footer">
        <el-button @click="showDetails = false">關閉</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
import studentsData from '../assets/json/students.json'
export default {
  data() {
    return {
      showDetails: false,
      students:studentsData
    };
  }
};
</script>
