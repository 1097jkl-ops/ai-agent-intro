# AI Agent Intro & Unit 5: 內建擴充套件與本地 AI 實作

本專案為人工智慧導論與 AI Agent 應用開發的學習與實踐紀錄，涵蓋從基礎的 API 與 Tool 觀念、平台擴充套件串接，到本地端 24/7 運行之 Discord 機器人整合。

---

## 📚 學習重點與核心觀念 (Unit 5)

1. **API 與 Tools 的轉化**：
   - **API 的限制**：傳統 API 結構複雜、充滿技術參數，不便於 AI 直接靈活調用。
   - **Tools（工具介面）**：將複雜 API 包裝成 AI 易於理解與操作的工具，讓 AI 具備呼叫外部功能的直覺能力。
2. **MCP 與 Skill（AI 專用使用手冊）**：
   - 透過 **Skill** 與 **MCP (Model Context Protocol)** 提供標準化說明書與協議，讓 AI 隨時清楚自己擁有哪些工具與領域知識。
3. **內建擴充套件串接**：
   - 於 Coze 平台串接 **Plugin-browser (LinkReader)** 等擴充外掛，讓客服 Agent 具備自動爬取、解讀網址及回答特定課程內容的能力。

---

## 🤖 本地端 OpenClaw 機器人實作

本專案同時在 Windows 本地端完成 OpenClaw 框架與 Discord 機器人的串接與常駐設定：

- **架構設計**：串接 Discord.py 與本地端模型（如 LM Studio），實現私訊與群組皆可正常互動的智慧代理人。
- **24/7 恆常運行設定**：
  - 調整 Windows 電源與睡眠設定，確保背景程式持續執行。
  - 透過 Windows **工作排程器** 設定使用者登入時自動執行啟動指令 (`cmd /c openclaw gateway start`)，實現開機自動上線。

---

## 🚀 快速啟動指令

若要在本地端啟動 OpenClaw Gateway 服務，請於終端機執行以下指令：

```bash
openclaw gateway start
