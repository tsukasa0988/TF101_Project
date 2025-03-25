# 🎖 TF101 任務製作標準範本集

📅 建立日期：2025-03-25  
✍️ 編寫人員：Vanguard  
📁 儲存位置：`/docs/Mission_Template_Guide.md`

---

## 📌 本文件目的

建立一份標準化的任務製作參考手冊，供 TF101 任務製作組（Vanguard / Ming）未來快速建立、調整、傳承任務架構使用。

---

## 🧱 標準任務資料夾結構（.mission）

```
任務名稱.地圖名稱/
├── mission.sqm                  # Eden 主場景檔
├── description.ext              # 任務設定與模組呼叫
├── stringtable.xml             # 任務中文提示
├── init.sqf                    # 初始化腳本
├── briefing.sqf                # 玩家任務簡報
├── scripts/                    # 所有支援腳本存放處
│   ├── support_call.sqf
│   └── enemy_wave.sqf
├── dialog/                     # 字幕與語音支援用
│   └── subtitles.hpp
├── README.md                   # 任務說明與紀錄備註
```

---

## 🧠 任務製作流程建議

### 1️⃣ 任務規劃階段
- 任務目標明確化（如：突襲、撤離、防守、搜尋）
- 劇情節點初步設計（使用 Markdown 流程圖列出）
- 決定使用模組（如：Simplex / ALiVE / ACE）

### 2️⃣ Eden 編輯器建構階段
- 建立基本場景（陣營、玩家角色、基地位置）
- 加入觸發區與邏輯模組
- 測試單人／小組進入是否流暢

### 3️⃣ 腳本整合階段
- 撰寫或整合支援呼叫腳本（空投／空襲／火砲）
- 加入 AI 波次腳本、時間觸發、地點感知等邏輯
- 測試 Init / onPlayerRespawn / 支援呼叫流程是否正常

### 4️⃣ 任務中文提示整合
- 使用 `stringtable.xml` 寫入所有顯示內容
- 搭配 `hint` / `task` / `briefing.sqf` 呼叫語系欄位
- 可擴充為語音播放 / 字幕同步（需搭配 `subtitles.hpp`）

### 5️⃣ 測試與封包
- LAN 模式進行 Alpha 測試
- 整理測試回饋，修正關鍵觸發與邏輯
- 封裝成 `.pbo` 交付給伺服器或正式使用

---

## 🎯 可擴充模組區塊

| 模組類型 | 範例與用途 |
|----------|------------|
| 戰術支援 | Simplex 支援模組（空投／空襲） |
| 動態戰場 | ALiVE 動態生成模組 |
| 體感強化 | ACE / RHS / TierOne（武器、醫療、裝備） |
| 劇情演出 | TaskForceRadio / 字幕 / VO 模組 |
| Zeus 監控 | 加入 Zeus 模組做任務導演與旁觀者支援 |

---

## 🗂 範例任務（推薦作為模板）

- `mission_1_ALIVE_TF101`：ALiVE 沙盒戰場任務骨幹
- `mission_2_RedWings`：劇情推進與觸發分支展示
- `OP_Kamdesh`：複合防禦型任務，含基地攻防與波次控制

---

## 📘 建議未來新增項目（規劃中）

- [ ] TF101_Story_Template.md（原創劇情規格模板）
- [ ] TF101_Trigger_Library.sqf（可複製套用的觸發範本庫）
- [ ] TF101_MissionCheckList.txt（任務製作與測試清單）

---

Vanguard 持續更新中，如需補充更多教學、語音整合、分支觸發進階設計，可擴充至《進階任務演出系統》。
