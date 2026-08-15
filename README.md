# sdd skill 安裝懶人包

單一 skill：以問答收集需求、自動判斷訪談風格、以 `.sdd/state.md` 里程碑續傳，產出 spec/design/tasks/evidence 四份文件，並可審查文件或 skill 自身。

## 安裝

把 `sdd/` 整個資料夾複製到 `~/.claude/skills/` 下：

```bash
mkdir -p ~/.claude/skills
cp -R sdd ~/.claude/skills/
```

（Windows：複製 `sdd` 資料夾到 `%USERPROFILE%\.claude\skills\` 下）

主目標是 **Claude Code personal skills**（`~/.claude/skills/sdd/`）。opencode 原生讀 `~/.claude/skills/`，安裝後自動可用，不需 junction。更新 = 重新覆蓋資料夾。

## 驗證

- Claude Code：輸入 `/` 看 `/sdd` 是否出現，或問「你有 sdd skill 嗎」
- opencode：問「你有 sdd skill 嗎」
- 沒出現就重開 session（最保險）

## 使用

1. 新 session 說「用 sdd 規劃這個專案」（或「繼續上一個 sdd 專案」）
2. skill 開場讀 `.sdd/<slug>/state.md` 接棒，或開新訪談
3. 依建議回答每題（每題都有推薦答案）
4. 完成後產出四份文件，sdd 會先審再往下走

## 檔案結構

```
sdd-skill/
├── sdd/
│   ├── SKILL.md                 # 薄 body：開場儀式、階段路由、audit 呼叫點
│   └── references/
│       ├── interview-rules.md   # grill-me 紀律 + rdq 四象限 + 互動預算
│       ├── question-bank.md     # 領域題庫
│       ├── spec-template.md     # 照 ai_coding_sample 慣例
│       ├── design-template.md
│       ├── tasks-template.md
│       ├── evidence-template.md
│       └── audit.md             # §A 審 skill / §B 審文件
└── README.md
```

## 設計原則（audit.md §A 可自我檢查）

- SKILL.md 保持薄（<60 行），大內容全在 references 按需讀入（漸進揭露）
- state.md 是唯一真相來源，里程碑式更新，跨 session 接棒
- 每題必附推薦答案、硬預算（3 輪 × ≤4 題）、隨時可喊停