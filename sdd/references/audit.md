# Audit

兩個用途：§A 審 skill 自身，§B 審產出的文件。跑完逐條列違規 + 修正建議，修完再跑一次到全過。

## §A 審 skill（審 sdd 自己）

> 偏見警告：agent 審「自己正在載入的 skill」會偏袒自己。**必須開新 session，不要載入 sdd，只 Read 檔案內容來審。**

- A1 **no-op 測試**：每句是否改變了 agent 的行為？agent 本來就會做的刪掉（整句刪，不刪字）。
- A2 **pointer 措辭**：references 的指向是否強到「必讀」程度？（如「先找 .sdd/ 讀 state.md」比「可用 state.md 續傳」強）
- A3 **single source of truth**：同一意思是否只放一處？有重複就併掉。
- A4 **negation 陷阱**：是否用「不要 X」引導？改成正向目標（寫「一題一題問」而非「不要連珠炮」）。
- A5 **漸進揭露**：大內容是否都在 references、SKILL.md 保持薄？（SKILL.md 應 <60 行）
- A6 **frontmatter**：`name` 是否小寫 kebab-case 且等於資料夾名？`description` 是否有值？

## §B 審文件（審 spec/design/tasks/evidence）

- B1 **與 state.md 一致**：所有 decided 都有對應、無矛盾。
- B2 **模板完整性**：骨架欄位都填滿？留空 = 沒想清楚。
- B3 **前後一致**：spec 每個需求在 design/tasks/evidence 都有歸宿，沒有孤兒需求。
- B4 **術語統一**：同一概念是否用同一個詞。
- B5 **驗收可測**：每條需求寫得出「怎麼證明完成」。
- B6 **範圍防禦**：non-goals 有列；沒有未宣告就塞進去的範圍。