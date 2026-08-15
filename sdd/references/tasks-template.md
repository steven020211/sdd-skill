# Tasks 模板

產出 `tasks.md`，對應 spec.md（要什麼）與 design.md（怎麼做）。每個任務完成後勾選對應驗收（AC）。產出後 Read `audit.md` §B 審查。

## # Tasks — {專案名}

> 對應 spec.md（要什麼）與 design.md（怎麼做）。每個任務完成後勾選對應驗收（AC）。

## 分層任務

### {層/模組名}

- [ ] T1 {一句話任務}
      → AC{編號}
- [ ] T2 {一句話任務}
      → AC{編號}

（依設計決策 D1…Dn 分層）

## 驗證

- [ ] T{n} {build/typecheck/test 命令} 無錯誤
- [ ] T{n+1} 執行程式，逐條對照 spec.md 的 AC 人工驗證
- [ ] T{n+2} 填寫 evidence.md（驗證結果紀錄）

## 執行順序

（T1 → T2 → …，寫出依賴關係與為何此順序）