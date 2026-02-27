# Go + Vue Demo Project

這是一個結合 Go 語言 backend 與 **Vue.js 3** frontend 的示範專案。透過 Vue 的現代化開發模式，實現一個簡單的 Single Page Interaction (SPI)。

## 🚀 如何執行專案 (Execution)

確保您的電腦已安裝 [Go](https://go.dev/doc/install)。

1. **開啟終端機** 並進入專案目錄。
2. **啟動伺服器**：
   ```powershell
   go run app.go
   ```
3. **瀏覽網頁**：
   開啟瀏覽器並造訪 [http://localhost:8080](http://localhost:8080)。

---

## 📂 `static` 目錄機制說明

`static` 目錄用於存放專案中的靜態前端資源，在 Go + Vue 的架構中扮演關鍵角色：

- **資源讀取**：`app.go` 使用 `http.ServeFile` 首次將 `static/index.html` 送至瀏覽器。
- **前端框架載入**：`index.html` 中透過 CDN 引入了 Vue.js 3：
  ```html
  <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
  ```
- **前後端互動**：Vue 內的 `fetch('/')` 函數會再次呼叫 Go 的 backend API。由於 Go 程式碼中的 `started` 旗標邏輯，後續的請求會直接回傳內容（如 `<p>🚀GET</p>`）而非 HTML 檔案，實現了簡單的數據交換。

---

## 🛠️ 開發設定 (Settings)

如果您使用 **GoLand** 進行開發，請確保已設定 `goimports` 以自動處理封裝導入：
- `File` -> `Settings` -> `Tools` -> `File Watchers` -> 新增 `goimports`




