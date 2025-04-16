# TF101 Project 任務與系統整合總覽
*更新時間：2025-04-15 XX:XX:XX*

---

## 🎖️ TF101 專案架構總覽

### 1. 技術 AI 分工
- **Specter**：模組整合技術官（MOD 分類／依賴分析／ALiVE 相容性）
- **Vanguard**：任務建構官（任務編輯／劇情邏輯／測試封裝）
- **Echo**：公關文案與 GitHub 文件整理、視覺統整

---

## 🗂️ 目前進行中任務

### 【任務一】TF101 沙盒戰區
- 模組：ALiVE + Simplex 中文化 + RHS + 自定義基地支援
- 地圖：Lythium
- 支援系統：空投、火砲、直升機整合支援
- 狀態：已完成 Alpha 測試，準備 Release 版本
- 待處理項目：
  - 加入任務簡報開場
  - 測試 Zeus / 支援指令中文顯示完整性

---

### 【任務二】紅翼行動（Lone Survivor）
- 劇情：夜間空投 → 牧民事件 → 敵軍圍剿 → 撤退／掩護
- 地圖：Takistan（還原真實場景）
- 單位：4人 SEAL 小隊
- 功能：劇情觸發、分支對話、空中支援
- 狀態：劇情邏輯建構中，等待音效與分支測試

---

### 【任務三】OP_Kamdesh（The Outpost）
- 地圖：山區基地還原（Kamdesh）
- 類型：山谷攻防戰（持久戰劇情）
- 狀態：已設計初步事件，等待據點還原與守軍配置

---

### 【任務四】Lythium Dynamic AI Warfare
- 類型：AI vs AI 動態沙盒，可由玩家自由介入或觀戰
- 使用模組：ALiVE + Simplex 中文 + ACE + KAT + RHS + 自定義派系
- 支援：隨機任務、生還者營救、AI 勢力戰略控場
- 狀態：Alpha 測試完成，Release 預定 4/17 前提交

---

## 🧩 MOD 結構與分類

- TF101 私模結構已劃分為：
  - Main / Core / SF / Effect / Outfit-XYI
- 依賴分析比對：
  - Afg_ALIVE_TF101.html → 常用模組精簡化完成
  - 將產出模組整合 Excel 對照表供 Specter 使用

---

## 📅 作業排程建議

| 任務代碼 | 任務名稱              | 預定交付版本 | 狀態         | 負責角色   |
|----------|----------------------|--------------|--------------|------------|
| OP001    | TF101 沙盒戰區       | Release版     | 進入封裝      | Vanguard   |
| OP002    | 紅翼行動             | Alpha 完成    | 分支劇情中    | Vanguard   |
| OP003    | OP_Kamdesh           | 初始規劃      | 擬真還原中    | Vanguard   |
| OP004    | Dynamic AI Warfare   | Release 4/17 | 測試中        | Vanguard   |
