# AIPost Future Circle｜Cohort 01 微型任務
## A｜AI 工具實測
### A1｜Fable 5 上工第一天

在 **AIPost Future Circle Cohort 01 微型任務**中，我選擇了 **A1｜Fable 5 上工第一天**，以「使用 AI 將業務流程轉換為 draw.io 流程圖」為實作主題。

本專案使用 Claude Fable 5、自訂 `flow-chart-creator` Skill 與 draw.io MCP，將去識別化的設備報修流程說明文件轉換為可編輯的 draw.io 流程圖，並透過人工檢查、修改與定稿，完成最終版本。

## 建議閱讀順序

1. [Google Drive｜專案完整檔案](https://drive.google.com/drive/folders/1OTAARsmZtawmmVK3D0NVaWkZh6mZgQ_J?usp=sharing)
2. [簡報](01-slides/AI工具實測_A1任務_胡怡欣.pptx)
3. [Demo 影片說明](02-demo-video/README.md)
4. [Task Prompt](03-prompt/task-prompt.md)
5. [Input](04-input/)
   - 5-1. [既有文件](04-input/01-existing-document/)｜[設備報修流程說明](04-input/01-existing-document/設備報修流程說明.md)
   - 5-2. [依模板建立](04-input/02-created-from-template/)｜[保險理賠申請流程說明](04-input/02-created-from-template/保險理賠申請流程說明.md)
6. [Output](05-output/)
   - 6-1. [AI 原始輸出](05-output/01-ai-original/)
   - 6-2. [人工修改版本](05-output/02-human-revised/)
7. [Skill｜flow-chart-creator](06-.claude/skills/flow-chart-creator/SKILL.md)
8. Reference
   - 8-1. [流程說明文件模板](06-.claude/skills/flow-chart-creator/references/flow-desc-template.md)
   - 8-2. [流程圖繪圖規格](06-.claude/skills/flow-chart-creator/references/drawing-spec.md)

> 若 GitHub 上有任何檔案無法預覽或下載，請改至 [Google Drive](https://drive.google.com/drive/folders/1OTAARsmZtawmmVK3D0NVaWkZh6mZgQ_J?usp=sharing) 查看。

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
│   └── AI工具實測_A1任務_胡怡欣.pptx
├── 02-demo-video/
│   └── README.md
├── 03-prompt/
│   └── task-prompt.md
├── 04-input/
│   ├── 01-existing-document/
│   │   └── 設備報修流程說明.md
│   └── 02-created-from-template/
│       └── 保險理賠申請流程說明.md
├── 05-output/
│   ├── 01-ai-original/
│   │   ├── 01-設備報修-子流程1-進入即時語音平台.png
│   │   ├── 02-設備報修-子流程2-申報人身份資訊確認.png
│   │   ├── 03-設備報修-子流程3-申報人名下設備顯示與選擇.png
│   │   ├── 04-設備報修-子流程4-設備問題描述與確認.png
│   │   ├── 05-設備報修-子流程5-建立設備報修單.png
│   │   ├── 06-設備報修-完整流程.png
│   │   └── 07-保險理賠流程圖.png
│   └── 02-human-revised/
│       ├── 01-人工修改-設備報修-子流程1-進入即時語音平台.png
│       ├── 02-人工修改-設備報修-子流程2-申報人身份資訊確認.png
│       ├── 03-人工修改-設備報修-子流程3-申報人名下設備顯示與選擇.png
│       ├── 04-人工修改-設備報修-子流程4-設備問題描述與確認.png
│       └── 05-人工修改-設備報修-子流程5-建立設備報修單.png
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
Jane HU
