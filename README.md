# vue2_element_ui_card_popupbox_table
這是一個使用 Vue 2 和 Element UI 建立的學生資料表格與彈出框顯示詳細資訊的範例專案。

在此專案中，我們將功能分為兩個組件：MainTable.vue 和 StudentDetailsDialog.vue。以下是對這兩個組件的簡要說明：

MainTable.vue：

此組件主要用於顯示學生的基本資料，包括姓名、生日和性別。當用戶在表格中點擊「查看學生詳情」按鈕時，將觸發彈出框（StudentDetailsDialog）顯示該學生的詳細資訊。

StudentDetailsDialog.vue：

此組件用於顯示學生的詳細資訊，包括姓名、生日、性別、年級和手機號碼。它以彈出框的形式顯示在主表格之上。當用戶點擊「關閉」按鈕時，彈出框將關閉並返回主表格。

將這兩個組件組合在一起，您將獲得一個可以顯示學生基本資料的表格，並且可以查看詳細資訊的彈出框。這樣的結構有助於保持代碼的整潔和模組化，讓維護和擴展變得更加容易。
## 專案設置
首先，安裝專案所需的依賴：
```
npm install
```

### 編譯並在開發環境中進行熱重載
使用以下命令啟動開發服務器，進行編譯和熱重載：
```
npm run serve
```

### 編譯並壓縮以便生產環境
使用以下命令對專案進行編譯和壓縮，以便在生產環境中部署：
```
npm run build
```

### 檢查並修復檔案
使用以下命令對專案中的檔案進行檢查和修復：
```
npm run lint
```

### 自訂配置
要查看有關自訂 Vue CLI 配置的更多資訊，請參閱 [Configuration Reference](https://cli.vuejs.org/config/).
