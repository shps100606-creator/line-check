# line-check 專案入口

- 程式碼結構、責任邊界與驗證方式：先讀 `CODEBASE-STRUCTURE.md`。
- 目前唯一程式入口是 `index.html`；HTML、CSS 與 JavaScript 共置，沒有後端、資料庫、登入或 repo 內建置流程。
- 現況以 current source 為準；不得把外部網址、部署狀態或 Production 可用性視為已驗證，除非另有即時證據。
- 修改 DOM、外部連結、內嵌腳本、瀏覽器儲存、公開 URL 或權限假設時，必須同步更新 `CODEBASE-STRUCTURE.md` 對應章節。
- 未經明確授權，不對正式網址或外部服務執行具副作用的操作。
