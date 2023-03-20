<template>
  <!-- 彈出框元件 -->
  <el-dialog :visible="visible" title="學生詳情" width="30%" @close="$emit('update:visible', false)">
    <!-- 表格顯示學生詳情 -->
    <el-table :data="[student]" border stripe>
      <!-- 循環渲染表格列 -->
      <el-table-column v-for="(column, index) in tableColumns" :key="index" :prop="column.prop" :label="column.label">
      </el-table-column>
    </el-table>
    <!-- 底部關閉按鈕 -->
    <span slot="footer" class="dialog-footer">
      <el-button @click="$emit('update:visible', false)">關閉</el-button>
    </span>
  </el-dialog>
</template>
<script>
  export default {
    // 接收從父組件傳入的屬性
    props: {
      visible: {
        type: Boolean,
        required: true,
      },
      student: {
        type: Object,
        required: true,
      },
    },
    data() {
      return {
        // 表格列配置
        tableColumns: [{
            prop: "name",
            label: "姓名"
          },
          {
            prop: "birthday",
            label: "生日"
          },
          {
            prop: "gender",
            label: "性別"
          },
          {
            prop: "grade",
            label: "年級"
          },
          {
            prop: "phone",
            label: "手機號碼"
          },
        ],
      };
    },
  };
</script>