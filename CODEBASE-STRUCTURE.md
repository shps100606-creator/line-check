# line-check 程式碼結構說明書

## 文件定位

- Current authority：本文件只描述目前單檔靜態 LINE 檢查頁的 as-built 結構。
- Baseline：`origin/main` at `7032fdd41b022b70f696d30463e39b471892e0fa`。
- Last verified：2026-10-28。
- Canonical entry：`CODEBASE-STRUCTURE.md#line-check-程式碼結構說明書`。
- Format authority：`claude-skills/AGENOTEs/agenote-write.md#四、CODEMAP 格式（程式碼結構說明書）`。

## 快速導航

| 查閱目的 | 模組鍵／章節 | Source／contract locator |
|---|---|---|
| 頁面、樣式與互動 | `STATIC-01`／`### STATIC-01｜單檔靜態頁` | `index.html` |

## 專案結構

```text
.
├── index.html                 # 唯一網站 source；HTML、CSS、JavaScript 共置
└── CODEBASE-STRUCTURE.md
```

## 模組地圖

### STATIC-01｜單檔靜態頁

- 責任：提供目前 repository 唯一的公開頁面、內嵌樣式與瀏覽器互動。
- 非責任：沒有後端、資料庫、登入、建置流程或獨立部署設定。
- 入口／route：`index.html`／`/`。
- Source／symbol：`index.html`；沒有可獨立引用的 module export。
- Data owner／write owner：頁面內的靜態文字與瀏覽器狀態由 `index.html` 擁有；沒有 server-side data owner。
- 必要依賴與原因：瀏覽器內建 HTML／CSS／JavaScript；外部資源若存在以 `index.html` 實際 URL 為準。
- Interface／contract：單一公開 URL 與 DOM event contract。
- Permission／trust boundary：公開頁；不可把瀏覽器輸入視為可信後端資料。
- Side effects：只限瀏覽器畫面／導向等前端效果；repo 沒有持久化寫入。
- Failure／retry：外部 URL 或瀏覽器 API 失敗時沒有 server retry；使用者只能重試或重新載入。
- Compatibility／migration：任何 DOM id、公開 URL 或內嵌 script 行為改動都可能直接影響既有使用者。
- Verification：以本機靜態伺服器開啟 `index.html`，檢查主流程、console 與所有外部連結。
- Lifecycle／current use：active source，但 repo 未提供 runtime／Production 驗收證據。
- Unknowns：正式部署位置、流量與最後一次 Production 驗證皆 unknown。

## 跨模組關係

目前只有一個 source module，沒有 repo 內跨模組依賴。

## 更新與驗證

- 更新觸發：`index.html` 的 DOM、外部連結、腳本、儲存或權限假設改變。
- 最小檢查：檔案存在、HTML 可載入、console 無阻斷錯誤、主要互動可重現。
- Runtime／production 未驗證項：正式網址與部署平台未在 repo 宣告；本次未做 Production 驗收。
