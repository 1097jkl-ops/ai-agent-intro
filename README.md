# 🌸 VN-Heroine-AI-Agent (Galgame 沉浸式動態角色互動與情感狀態 Agent)

## 1. 應用場景 (Use Case)
* **目標產品**：Galgame（視覺小說）動態 NPC 陪伴、隱藏聊天分支或同人劇本輔助生成工具。
* **使用對象**：Galgame 沉浸式玩家、視覺小說（VN）同人創作者。
* **痛點**：傳統 Galgame 對話為預錄分支（Linear/Branching script），選項選完就結束，無法與女主角進行具有長期記憶與自適應口癖（Persona）的自由對話；創作者在寫日常高互動支線時也常面臨角色 OOC（超出人設）困境。
* **Agent 價值**：結合嚴格 Character Prompt（口癖與心理防衛機制）、Lorebook RAG（世界觀記憶檢索）與 State Machine（好感度/狀態變數），實現兼具沉浸感與角色不崩壞的動態對話體驗。

## 2. 核心名詞與知識結構 (Core Terms & Knowledge Structure)
| 知識層級 | 核心名詞 | 說明與架構定義 |
| :--- | :--- | :--- |
| **基礎層** | **Character Prompt (人設約束)** | 定義角色口癖、背景故事、心理陰影與說話氣場（防止 OOC）。 |
| | **Lorebook (世界觀設定集)** | 儲存專屬地名、道具、事件時間軸的結構化背景。 |
| **工具層** | **State Machine / Variable (狀態機)** | 動態記錄玩家與角色的「好感度 (Affection)」與「階段進度」。 |
| | **Memory RAG (長期記憶檢索)** | 檢索玩家過去對話提及的承諾或喜好片段。 |
| **流程層** | **Node / Flow (Coze 節點)** | 狀態更新 $\rightarrow$ 記憶檢索 $\rightarrow$ 角色生成 $\rightarrow$ 表情/好感回饋。 |

## 3. Coze 拖拉式 Agent 工作流程構想 (Workflow Architecture)
```text
[使用者輸入 User Input]
       │
       ▼
[State/Affection Update (好感度與狀態更新節點)]
       │
       ▼
[Lorebook & Memory RAG 檢索]
       │
       ▼
[Character Prompt 約束生成 LLM 節點]
       │
       ▼
[Output: 對白 + 表情/心理描寫 + 狀態變數更新]
