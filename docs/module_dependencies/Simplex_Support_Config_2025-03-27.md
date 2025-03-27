# 🔧 Simplex 支援系統中文化對應建議
📅 產出日期：2025-03-27  
📂 分類：模組中文化建議  
✍️ 製作：Vanguard

---

## 📘 中文化建議方向

本文件針對 Simplex Support Services 模組的主要功能選單與 UI 元素進行中文化可行性分析與對應方式建議，預計整合至 TF101 ALiVE 任務中。

---

## ✅ 關鍵翻譯項目

| 顯示項目 | 英文原文 | 建議繁體翻譯 |
|-----------|-----------|----------------|
| 支援類型：運輸 | `Transport` | 運輸支援 |
| 支援類型：攻擊 | `CAS` | 近接空中支援 |
| 支援類型：砲擊 | `Artillery` | 火砲支援 |
| 支援類型：物資 | `Resupply` | 彈藥補給 |
| 支援類型：偵察 | `Recon` | 偵察飛行 |
| 支援狀態提示 | `Support incoming!` | 支援來襲中！ |
| 呼叫完成提示 | `Support delivered.` | 支援已完成。 |

---

## 🗂️ 實作建議方式

### ✅ 方法一：新增 `stringtable.xml`

- 若原模組未內建，可新增語系欄位 `ChineseTraditional`
- 每個支援項目加入對應 `<Key>`，並在 `description.ext` 中指定語系：

```sqf
language = "ChineseTraditional";
```

### ✅ 方法二：直接修改 SQF 字串

- 修改檔案：`fn_displaySupportMenu.sqf` 等
- 替換內文直接輸出的英文為繁體字串（適合快速修改但不利多語系切換）

---

## 🧩 延伸整合建議

| 任務需求 | 對應處理 |
|-----------|-----------|
| 需要多人皆可操作 | 在 Eden 內設置 `Simplex Operator Module` 並開啟 "All players" 權限 |
| 自訂支援載具類型 | 編輯 `config.cpp` 或自建支援定義模組 |
| 結合任務條件觸發 | 於任務中嵌入 `callSupport` 條件，例如完成目標後才允許呼叫支援 |

---

📘 若需進一步結合 ALiVE/劇情觸發，我可提供範例腳本與模組化擴充設定方式。

