# ComfyUI Cloud、MCP 與 MiniMax H3 研究

整理日期：2026-10-30。以下為文件研究結果，尚未使用帳號執行生成驗證。

## 建議路徑

中文需求 → Codex → 官方 Comfy Cloud MCP → H3 官方模板 → 雲端生成 → 取得輸出。

已有官方 MCP，無須先自行開發轉接伺服器。官方端點為 `https://cloud.comfy.org/mcp`，可透過 OAuth 登入帳號。Discovery 查詢可使用一般 Comfy 帳號；執行生成需有效 Cloud 訂閱，只有剩餘點數不夠。

來源：[Comfy MCP](https://docs.comfy.org/agent-tools/mcp)。

## MiniMax H3

官方指南列出文字生影片（T2V）、圖片生影片（I2V）、參考素材生影片（R2V）、多影格參考和 ControlNet 等流程，並支援原生立體聲音訊。開放權重的目標約為 1 百萬像素、短邊 768px、24fps、最長約 15 秒；2K 輸出需要額外升頻流程。這些是模型指南資訊，並非本控制台保證支援的選項。

Comfy Cloud 的生成已包含商用權利；本機生成商用須依官方授權規則辦理。

來源：[MiniMax H3 官方指南](https://docs.comfy.org/tutorials/video/minimax/minimax-h3)。

## MCP 可處理的工作

可查詢模板、模型、節點及模板可覆寫參數；可執行模板或自訂工作流程、上傳素材、查看任務、取消任務及取回輸出，也可操作已儲存工作流程。

對此專案而言，應先確認連線、帳號狀態與 H3 模板，再選用符合需求的模板。費用資訊若查不到，應明確表示未知，不把估算當成服務保證。

官方另提供 `create_app` 和 `get_app_mode_url`，可以把已儲存工作流程變成簡化 App Mode。這是連接帳號後建立正式操作頁的候選方式。

來源：[官方 MCP 工具列表](https://docs.comfy.org/agent-tools/mcp)。

## 自建完整介面的替代方案

若 App Mode 無法滿足需求，可使用 Comfy SDK／API 建立自有前後端。官方建議執行工作流程優先使用 Comfy API v2 或 SDK；舊版 v1 Cloud API 已標示 deprecated，但仍提供部分 Cloud 專屬功能。自建介面應將憑證留在後端，並提供真正的任務狀態與輸出。

來源：[Cloud Quickstart](https://docs.comfy.org/development/deploy/cloud)、[Cloud API Overview](https://docs.comfy.org/development/cloud/overview)、[取得 API Key](https://docs.comfy.org/development/api-development/getting-an-api-key)。

## 本次交付範圍

已完成命令整理介面與中文操作說明。尚未連接帳號、確認帳號可用模板、取得實際費用、執行影片生成或建立 App Mode。
