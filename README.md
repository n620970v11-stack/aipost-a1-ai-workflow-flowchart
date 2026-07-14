# AIPost A1｜使用 AI 將業務流程轉換為 draw.io 流程圖

本專案為 **AIPost Future Circle Cohort 01 微型任務 A1｜Fable 5 上工第一天**的實作紀錄。

我使用 Claude Fable 5、自訂 `flow-chart-creator` Skill 與 draw.io MCP，將去識別化的設備報修流程說明文件轉換為可編輯的 draw.io 流程圖，並保留人工檢查、修改與定稿流程。

## 建議閱讀順序

1. 簡報
2. [Demo 影片｜子流程 1：進入即時語音平台](02-demo-video/Flow1-進入即時語音平台.mov)
3. [Task Prompt](03-prompt/task-prompt.md)
4. [Input｜設備報修流程說明文件](04-input/設備報修流程說明.md)
5. Output
6. [Skill｜flow-chart-creator](06-.claude/skills/flow-chart-creator/SKILL.md)
7. Reference
   - 7-1. [流程說明文件模板](06-.claude/skills/flow-chart-creator/references/flow-desc-template.md)
   - 7-2. [流程圖繪圖規格](06-.claude/skills/flow-chart-creator/references/drawing-spec.md)

## 工作流程

```text
Task Prompt
→ flow-chart-creator Skill
→ 分析既有流程說明文件，或引導使用者建立流程說明文件
→ 使用者確認流程內容
→ Claude Fable 5 生成 draw.io XML
→ draw.io MCP 開啟網頁版
→ 人工檢查、修改與定稿
```

## 使用工具與用途

| 工具 | 本次用途 |
|---|---|
| Claude Fable 5 | 分析流程文件並生成 draw.io XML |
| Claude Code | 執行 Task Prompt、載入 Skill 及呼叫 MCP |
| `flow-chart-creator` Skill | 規範流程梳理、確認、繪圖及檢查步驟 |
| draw.io MCP | 接收 XML 並開啟 draw.io 網頁版 |
| draw.io 網頁版 | 渲染、人工修改及定稿流程圖 |

## 資料夾結構

```text
aipost-a1-ai-workflow-flowchart/
├── README.md
├── 01-slides/
│   └── A1_簡報架構與內容.md
├── 02-demo-video/
│   └── Flow1-進入即時語音平台.mov
├── 03-prompt/
│   └── task-prompt.md
├── 04-input/
│   └── 設備報修流程說明.md
├── 05-output/
│   ├── ai-original/
│   └── human-revised/
└── 06-.claude/
    └── skills/
        └── flow-chart-creator/
            ├── SKILL.md
            └── references/
                ├── flow-desc-template.md
                └── drawing-spec.md
```

## 公開資料說明

- 本專案輸入文件已進行去識別化處理。
- Repository 不包含公司內部入口、帳號資訊、API 金鑰或本機 Claude Code 權限設定。

## 作者

`n620970v11`
