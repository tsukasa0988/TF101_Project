# 📦 TF101_HC_Deploy_Guide.md

本文件說明如何將一台舊主機部署為 Arma 3 的 Headless Client（HC）伺服端，供 TF101 任務使用，適用於 LAN 模式或遠端專用伺服器。

---

## ✅ 一、基本需求

### 必須準備：

- 一台 Windows 主機（建議使用舊電腦或副機）
- 安裝 Steam + Arma 3（無須啟動畫面）
- Steam 帳號（可共用主帳號，也可用小號）

---

## 🖥 二、硬體最低建議（以單一 HC 為例）

| 項目 | 建議配備 |
|------|----------|
| CPU | Intel i5 / AMD R5（4 核心以上） |
| RAM | 至少 8GB |
| 儲存空間 | 50GB（Arma 本體 + MOD） |

✅ **你的舊主機（AMD 5600X / RTX3060Ti / 32GB RAM）完全足夠擔任 HC 用途，甚至能作為輕量主伺服器使用。**

---

## 🔧 三、設定步驟

### 步驟 1：複製主機的 Arma 安裝與 MOD 至 HC 主機

可使用以下工具：

- 透過 USB 或內網複製整個 Arma 3 資料夾
- Workshop MOD 同步後放入相同資料夾結構（SteamCMD 亦可）

### 步驟 2：建立 HC 啟動批次檔（.bat）

```bat
start "" "arma3_x64.exe" -client -connect=127.0.0.1 -port=2302 -mod=@yourmods;@alive;@tf101 -name=HC -profiles=HC -nologs -noPause -hugepages -filePatching
```

> 可根據需要修改 -connect 與 -mod 清單。

### 步驟 3：確保 `description.ext` 設定包含 HC 白名單

```sqf
headlessClients[] = { "192.168.1.101" };  // 請改為 HC 主機的 IP
localClient[] = { "192.168.1.101" };
```

### 步驟 4：防火牆設定允許連接（LAN / 網路）

- 放行 Arma 所需的 Port（如 2302, 2304）
- 同時允許 HC 主機可存取遊戲主機 IP

---

## 📎 四、可選擇搭配的模組或工具

- `-filePatching` 可用於讀取任務外部設定
- `-profiles` 指定使用者與 log 儲存
- HC 建議禁用視覺與聲音資源，降低資源佔用

---

## 🧩 五、常見問題

| 問題 | 解法 |
|------|------|
| HC 無法連入 | 確認 IP / Port 是否正確、防火牆是否開啟 |
| HC 啟動但不執行 AI | 任務中是否未將 AI owner 遷移至 HC（可透過 ALiVE 檢查） |
| 使用相同帳號會被踢出？ | 建議 HC 使用不同 Steam 帳號或啟用 Steam 離線模式 |

---

如需部署進階版 HC + Zeus 雙用系統，Specter 可額外提供高階腳本與分流範本！
