<template>
  <!-- 這是一個 Vue.js 組件，它使用 Element-UI 庫中的 el-dialog、el-table 組件來顯示學生的詳細信息。 -->


  <!-- 使用 el-dialog 組件顯示對話框，visible 屬性用於控制對話框的顯示狀態，title 屬性設置對話框的標題，width 屬性設置對話框的寬度，@close 事件用於在關閉對話框時發出事件通知父組件修改 visible 屬性的值 -->
  <el-dialog :visible="visible" title="學生詳情" width="60%" @close="$emit('update:visible', false)">
    <!-- 使用 el-table 組件顯示表格，data 屬性指定表格數據，border 和 stripe 屬性控制表格是否顯示邊框和斑馬線 -->
    <el-table :data="[student]" border stripe>
      <!-- 使用 v-for 指令循環遍歷 tableColumns 數組，以生成每一個 el-table-column 組件 -->
      <el-table-column v-for="(column, index) in tableColumns" :key="index" :prop="column.prop" :label="column.label">
      </el-table-column>
    </el-table>
    <br />
    <!-- 顯示家長資料標題 -->
    <h3>家長資料</h3>
    <!-- 使用 el-table 組件顯示家長資料表格，data 屬性指定表格數據，formatter 屬性用於格式化表格數據 -->
    <el-table :data="student.parents" border stripe>
      <el-table-column prop="partent" label="身份" :formatter="row => (row.parent1 ? '父親' : '母親')">
      </el-table-column>
      <el-table-column prop="name" label="姓名"></el-table-column>
      <el-table-column prop="phone" label="電話"></el-table-column>
    </el-table>
    <!-- 使用 slot 插槽顯示對話框的頁腳，class 屬性指定頁腳的 CSS 類名稱 -->
    <span slot="footer" class="dialog-footer">
      <!-- 使用 el-button 組件顯示關閉按鈕，@click 事件用於在點擊按鈕時發出事件通知父組件修改 visible 屬性的值 -->
      <el-button @click="$emit('update:visible', false)">關閉</el-button>
    </span>
  </el-dialog>
</template>


<script>
  export default {
    // 定義 props，用於接收父組件傳遞的數據
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
        // 定義學生信息表格的表頭
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
        // 定義家長信息表格的表頭
        parentTableColumns: [{
            prop: "partent1",
            label: "父親"
          },
          {
            prop: "name",
            label: "姓名"
          },
          {
            prop: "phone",
            label: "手機號碼"
          },
          {
            prop: "partent2",
            label: "母親"
          },
          {
            prop: "name",
            label: "姓名"
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