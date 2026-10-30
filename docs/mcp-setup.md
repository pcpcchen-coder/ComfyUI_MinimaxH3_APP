# 官方 MCP 連接方式

## 使用 Codex 設定

1. 開啟設定 → MCP servers → 新增伺服器。
2. 選擇 Streamable HTTP。
3. 名稱填 `comfy-cloud`，URL 填 `https://cloud.comfy.org/mcp`。
4. 儲存後按 Authenticate，在登入頁使用自己的 Comfy 帳號授權並選擇工作區。
5. 回到對話，要求檢查連線和搜尋 MiniMax H3 模板。若工具尚未載入，重新開啟對話或依客戶端提示重新啟動。

## 使用 Codex CLI

若已安裝 Codex CLI，可執行官方文件列出的命令：

```sh
codex mcp add comfy-cloud --url https://cloud.comfy.org/mcp
codex mcp login comfy-cloud
```

此步驟會修改 MCP 設定並啟動帳號登入。本專案沒有自動執行這些命令。

## 驗證

請助理確認伺服器與授權狀態，再檢查訂閱／點數、搜尋 H3 模板並讀取參數定義。查詢成功後才提交生成。帳號有點數不代表訂閱仍有效。

本專案頁面的選項只產生文字需求，不代表已向 Cloud 驗證可用性。頁面不含 API key 輸入，也不直接呼叫生成端點。

## 正式簡化 UI

官方 MCP 提供 `create_app`，可將已儲存工作流程建立為 App Mode，再用 `get_app_mode_url` 取得操作連結。須等帳號連線、模板與輸入輸出確認後才能建立。

## 官方文件

- [Comfy MCP（含 Codex 設定與工具列表）](https://docs.comfy.org/agent-tools/mcp)
- [Codex MCP 文件](https://developers.openai.com/codex/mcp)
- [MiniMax H3 指南](https://docs.comfy.org/tutorials/video/minimax/minimax-h3)
