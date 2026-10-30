# ComfyUI MiniMax H3 APP

使用中文命令，透過官方 Comfy Cloud MCP 操作 MiniMax H3 的研究與簡易控制台。

**目前狀態：命令整理與介面預覽。尚未實作直接生成影片的後端，也沒有連接使用者帳號。使用此頁不會提交生成或消耗 Comfy 點數。**

## 使用控制台

下載此專案，以瀏覽器開啟 [`index.html`](index.html)。選擇創作方式、比例、秒數及版本數，輸入畫面與聲音需求，再按「複製命令」，貼到已連接 Comfy Cloud MCP 的 Codex 對話。

圖片／參考素材模式需另在對話附上素材或提供本機檔案路徑。頁面不會上傳素材。

比例與秒數是創作偏好，實際支援範圍需由 MCP 查詢所選模板後確認。頁面不提供虛構的點數估價。

## 連接 Comfy Cloud

在 Codex 設定的 MCP servers 中新增 Streamable HTTP 伺服器：

```text
名稱：comfy-cloud
URL：https://cloud.comfy.org/mcp
```

儲存後按 Authenticate，使用自己的 Comfy 帳號登入並授權。不要把密碼、API key 或登入憑證放入本專案。

執行生成需要有效的 Comfy Cloud 訂閱；只有儲值點數不足以取得執行權限。設定完成後，可要求 Codex 先檢查連線、訂閱、可用 H3 模板與參數，再決定是否生成。

## 檔案

- [`index.html`](index.html)：獨立網頁版；可複製中文命令。
- [`ui/comfy-h3-command.html`](ui/comfy-h3-command.html)：原始對話內介面，使用支援的宿主 API 送出後續檢查要求。
- [`docs/research.md`](docs/research.md)：官方資料、模型能力與限制。
- [`docs/commands.md`](docs/commands.md)：可直接使用的中文命令範例。
- [`docs/mcp-setup.md`](docs/mcp-setup.md)：MCP 登入、驗證與 App Mode 後續方案。

## 後續可實作

連接帳號後，以官方 H3 模板建立 Comfy App Mode，讓操作頁只顯示必要輸入與結果。此階段尚未建立 App Mode，也未部署 GitHub Pages 或其他線上網站。

研究整理日期：2026-10-30。服務功能與方案以官方文件及登入後實際查詢結果為準。
