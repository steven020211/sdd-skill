---
name: sdd
description: |-
  Spec-Driven Development 單一入口。以問答收集需求、自動判斷訪談風格、以
  .sdd/state.md 里程碑續傳，產出 spec/design/tasks/evidence 四份文件，並可審查
  文件或 skill 自身。使用時機：使用者想規劃一個軟體專案、或延續一個已有
  .sdd/state.md 的專案、或想檢查 skill 本身的品質。
license: MIT
compatibility: claude-code, opencode
metadata:
  audience: developers
---

# SDD 主流程

適合「腦子一片空白、不想想太多」的使用者。agent 主動扛起思考負擔。

## 開場儀式（接棒必讀，新 session 第一步）

1. 先找專案下 `.sdd/` 目錄。
   - 存在 → Read `.sdd/<最新 slug>/state.md`，依 `phase` 欄位續傳，跳到對應階段。
   - 不存在 → 新專案，走 Phase 0。
2. 全程繁體中文（台灣用語）。不知道的事就說不知道，不猜。

## Phase 0 · 需求蒐集（brain-blank onboarding）

- 使用者只給一句話也沒關係，從那句話開始逐題問。
- 每題必附「推薦答案」，一次只問一題，等回覆再問下一題。
- 依回答內容自動選訪談風格，寫進 state.md 的 `approach`：
  - 使用者已有具體計畫/想被挑戰 → 走 grill-me 紀律（interview-rules.md 前半）
  - 資訊零散/挖隱藏需求/綠地 → 走 rdq 紀律（interview-rules.md 後半）
- 硬預算：資訊夠就零題直接出檔；否則最多 3 輪、每輪 ≤4 題。使用者可隨時喊停。
- 每輪結束 → 里程碑式更新 state.md。進入 Phase 1。

## 階段路由（依 state.phase）

- `interview` → 繼續問答（Read `references/interview-rules.md`，需要時 Read `references/question-bank.md`）
- `spec` → 產 `spec.md`（Read `references/spec-template.md`）
- `design` → 產 `design.md`（Read `references/design-template.md`）
- `tasks` → 產 `tasks.md`（Read `references/tasks-template.md`）
- `evidence` → 產 `evidence.md`（Read `references/evidence-template.md`）
- 每階段產出文件後 → Read `references/audit.md` 的 §B 審該文件，通過才更新 state.phase。
- 完成一階段後，建議使用者換新 session 再接（state.md 已落盤）。

## 不變原則

- 每題必附推薦答案；一次一題。
- state.md 是唯一真相來源：決定落定就記，避免重問。
- 使用者說「檢查/audit」→ Read `references/audit.md`，依請求跑 §A（審 skill）或 §B（審文件）。

## 狀態檔 schema（`.sdd/<slug>/state.md`）

- `phase`：interview / spec / design / tasks / evidence
- `approach`：grill-me / rdq
- `decided`：已決定的事（決定 + 為何）
- `open_questions`：要問的問題清單（每題含推薦答案）
- `assumptions`：待確認的假設
- `out_of_scope`：範圍外
- `next_step`：下一步