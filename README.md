# AIPost A1｜使用 AI 將業務流程轉換為 draw.io 流程圖

## 本次選擇任務

**A1｜Fable 5 上工第一天**

本專案實測 Claude Code 搭配自訂 Skill 與 draw.io MCP，協助使用者梳理業務流程，並產生可編輯的 draw.io 流程圖。

本次實測包含兩種使用情境：

1. **已有流程說明文件**：AI 讀取既有文件、分析流程內容並產生流程圖。
2. **尚無流程說明文件**：AI 依照既定模板，透過互動引導使用者整理流程內容，再產生流程圖。

本次將使用 Claude Fable 5 模型協助產製流程圖。

## 建議閱讀順序

### 1. 閱讀成果簡報

成果簡報為本次任務的主要交付內容，並依照 A1 任務要求呈現以下內容：

- 任務背景
- 使用的 Prompt 與操作流程
- 原始輸出與人工修改處（以對照方式呈現）
- 實際節省多少時間
- 本次使用模型與工具的三項優點與三項限制
- 推薦給誰、不推薦給誰

成果簡報：

- [PDF 版本](01-slides/aipost-a1-presentation.pdf)
- [PowerPoint 原始檔](01-slides/aipost-a1-presentation.pptx)

### 2. 觀看 Demo 影片

Demo 影片呈現 Claude Code、自訂 Skill 與 draw.io MCP 的實際操作過程：

- [Demo 01｜已有流程說明文件](02-demo-video/demo-existing-document.mp4)
- [Demo 02｜尚無流程說明文件](02-demo-video/demo-without-document.mp4)

### 3. 查看專案相關資料

本 Repository 收錄本次實測所使用的輸入資料、Prompt、Skill、參考模板、繪圖規格，以及 AI 產出的流程圖檔案。

## 資料夾結構

```text
aipost-a1-ai-workflow-flowchart/
├── README.md
├── 01-slides/
│   ├── aipost-a1-presentation.pdf
│   └── aipost-a1-presentation.pptx
├── 02-demo-video/
│   ├── demo-existing-document.mp4
│   └── demo-without-document.mp4
├── 03-prompt/
│   └── task-prompt.md
├── 04-input/
│   └── equipment-repair-workflow-anonymized.md
├── 05-output/
│   ├── existing-document/
│   └── without-document/
└── 06-.claude/
    └── skills/
        └── flow-chart-creator/
            ├── SKILL.md
            └── references/
                ├── flow-desc-template.md
                └── drawing-spec.md
```

## 資料夾與檔案說明

### `README.md`

本專案的入口頁，提供專案簡介、建議閱讀順序、成果簡報與 Demo 影片入口，以及 Repository 資料夾與檔案說明。完整實測過程、成果比較與個人判斷，主要呈現在成果簡報中。

### `01-slides/`

放置本次任務的成果簡報：

- `aipost-a1-presentation.pdf`：供評審直接預覽與閱讀的主要版本。
- `aipost-a1-presentation.pptx`：簡報原始檔案。

### `02-demo-video/`

放置本次實測的 Demo 影片：

- `demo-existing-document.mp4`：呈現使用者已有流程說明文件時，AI 讀取文件、分析流程並產生流程圖的操作過程。
- `demo-without-document.mp4`：呈現使用者尚無流程說明文件時，AI 依模板引導整理流程內容，再產生流程圖的操作過程。

### `03-prompt/`

放置本次實測使用的 Prompt。

- `task-prompt.md`：用於啟動業務流程梳理與流程圖生成任務，並請 AI 先確認使用者是否已有流程說明文件。

### `04-input/`

放置「已有流程說明文件」使用情境的輸入資料。

- `equipment-repair-workflow-anonymized.md`：本次實測使用的去識別化業務流程說明文件。

### `05-output/`

放置兩種使用情境產生的輸出成果：

- `existing-document/`：已有流程說明文件情境的輸出成果。
- `without-document/`：尚無流程說明文件情境的輸出成果。

### `06-.claude/skills/flow-chart-creator/`

放置 Claude Code 實際使用的自訂 Skill 與相關參考資料：

- `SKILL.md`：定義 AI 執行業務流程梳理與 draw.io 流程圖生成任務時，應遵循的互動流程、分析方式、工具使用規則與檢查步驟。
- `references/flow-desc-template.md`：流程說明文件模板。當使用者尚未有流程說明文件時，AI 會讀取此模板，依照模板欄位引導使用者補充必要資訊，並整理成結構化的流程說明文件。
- `references/drawing-spec.md`：draw.io 流程圖的繪圖規格，包含節點樣式、色彩、版面配置、間距、連線方式與可讀性要求。
