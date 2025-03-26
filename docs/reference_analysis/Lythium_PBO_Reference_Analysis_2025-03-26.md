# 📘 參考任務分析報告｜Lythium_alive_V8.lythium
📅 分析日期：2025-03-26  
✍️ 分析人員：Vanguard

---

## 🔍 任務基本資訊

- 檔名：`Lythium_alive_V8.lythium`
- 類型：ALiVE 多熱區動態戰場
- 狀態：`.sqm` 為加密格式（二進位），無法直接解析物件配置

---

## ✅ 結構重點分析

### 🔹 description.ext
```cpp
class CfgFunctions {
    #include "INC_persist\\cfgFunctions.hpp"
};
class CfgRemoteExec {
    class Functions {
        mode = 2;
        jip = 1;
        #include "INC_persist\\functionsWhitelist.hpp"
    };
};
```

- 採用自建模組 `INC_persist` 控制任務進程持久化
- 多個 remoteExec 自訂函數呼叫，適合用於儲存／載入

### 🔹 可參考轉化重點

| 元件 | 說明 |
|------|------|
| 熱區任務結構 | 預設有多個 Profile 任務熱點，可推估為 3 區域分戰方式 |
| Profile 高密度佈局 | 適合進行 FPS 測試與 Profile 限制調控實驗 |
| 自定模組 | `INC_persist` 架構可推薦給 Specter 研究未來加入 Save/Load 模組 |

---
