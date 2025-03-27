# 🧠 TF101 無頭客戶端（HC）系統設計草案

本文件概述 TF101 任務中整合無頭客戶端（Headless Client, HC）的基本設計架構與實作策略，提升大型任務中的效能與穩定性。

---

## 📌 一、HC 概念簡述

- **Headless Client（HC）** 是不進行渲染畫面的 Arma 客戶端
- 專門負責執行 AI 控制／腳本運算，減少玩家主機負載

---

## 🛠 二、TF101 任務 HC 結構規劃

### 1. 任務內部設定（description.ext）

```sqf
headlessClients[] = { "127.0.0.1" };  // 或使用伺服器 IP
localClient[] = { "127.0.0.1" };
```

### 2. 腳本控制（init.sqf）

```sqf
if (isHeadlessClient) then {
    diag_log "HC: Headless Client 已啟動";
};
```

### 3. ALiVE 整合建議

- 透過 ALiVE 自帶模組設定 HC owner 自動分配
- 可與 Specter 共同確認 AI profile owner 自動遷移機制

---

## 🌐 三、遠端主機租賃與建議平台

| 主機平台 | 適合等級 | 備註 |
|----------|----------|------|
| Hetzner / OVH | 專業 | 穩定、歐洲地區延遲低 |
| DigitalOcean / Linode | 入門 | 簡單部署，適合測試 |
| AWS / GCP | 企業 | 彈性強，但收費較高 |
| GTXGaming 等遊戲主機平台 | 使用者友善 | 提供 Arma HC 支援，後台管理簡單 |

---

## ✅ 四、未來可擴展項目

- 📦 《TF101_HC_Deploy_Guide.md》：完整從部署到介接流程教學
- 🧩 HC + Zeus 支援整合範本
- 🔄 Dynamic HC 分配模組（Specter 可支援）

---

設計由 Vanguard 與 Specter 協同整備，作為 TF101 任務模組化優化項目之一。
