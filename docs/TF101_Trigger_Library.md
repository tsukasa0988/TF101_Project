# 🧩 TF101 任務觸發範本庫

📅 建立日期：2025-03-26  
✍️ 編寫人員：Vanguard  
📁 儲存位置：`/docs/TF101_Trigger_Library.md`

---

## 📌 本文件目的

本文件整理常見任務製作中會用到的各類觸發邏輯、條件語法與套用範例，供 TF101 任務開發組在 Eden 或腳本整合時快速複製、微調使用，加速任務設計流程。

---

## 🚪 基礎區觸發（Trigger）

### 🎯 玩家進入區域
**條件語法：**
```sqf
this && (player in thisList)
```

---

### 🎯 所有玩家進入
**條件語法：**
```sqf
{_x in thisList} count playableUnits == ({alive _x} count playableUnits)
```

---

### 🎯 特定單位進入
**條件語法：**
```sqf
(unit1 in thisList)
```

---

## ⏱ 時間延遲與循環觸發

### ⏳ 延遲幾秒後執行
```sqf
[] spawn {
    sleep 5;
    hint "已經過 5 秒！";
};
```

---

### 🔁 每 X 秒重複執行
```sqf
[] spawn {
    while {true} do {
        hint "每 10 秒顯示一次";
        sleep 10;
    };
};
```

---

## 📦 波次生成／敵軍觸發

### 👥 產生敵方小隊
```sqf
_grp = [getMarkerPos "enemy_spawn", EAST, ["O_Soldier_F", "O_Soldier_AR_F", "O_medic_F"]] call BIS_fnc_spawnGroup;
```

---

### 🧨 AI 感知觸發（見到玩家）
```sqf
player knowsAbout enemy_unit > 1.5
```

---

## 📢 任務提示／任務控制

### ✅ 設定任務成功
```sqf
["mainTask", "SUCCEEDED", true] call BIS_fnc_taskSetState;
```

### ❌ 任務失敗
```sqf
["mainTask", "FAILED", true] call BIS_fnc_taskSetState;
```

### 📜 顯示提示語
```sqf
hint "你找到情報了，繼續前進！";
```

---

## 🎬 特殊演出建議（進階演出可擴充至腳本包）

| 類型 | 技術建議 |
|------|----------|
| 鏡頭動畫 | 使用 `BIS_fnc_camera` 或 Cutscene Tools |
| 字幕顯示 | 建立 subtitles.hpp，並搭配 BIS_fnc_showSubtitle 呼叫 |
| 語音播放 | 使用 `playSound3D` 或 `say3D` 與 trigger 配合 |
| 時間停止 | `enableTimeAcceleration false` 配合 cutscene 呈現 |

---

本文件將持續擴充，未來可與 VO 系統、對話選項、任務分支模板進行整合。  
如有建議腳本片段，也可由 TF101 成員提交補充！

