# TF101 本地任務伺服器部署指南（適用於 LAN / 測試環境）

此指南適用於 TF101 任務開發者／測試人員，欲於本地部署 Arma 3 測試用伺服器時，提供一個簡單、乾淨且穩定的伺服器設置流程（不含 HC）。本教學涵蓋：資料夾結構、參數啟動、模組管理與任務封包放置流程。

---

## ✅ 1. 建立伺服器啟動用資料夾（建議非 Steam 路徑）

請先將 Arma 3 主程式備份一份至其他路徑（例：`D:/Arma3_Server`），避免與主用戶端混淆。

```
Arma3_Server/
├── arma3server_x64.exe
├── steam_appid.txt
├── mods/
├── keys/
├── MPMissions/
├── server.cfg
├── basic.cfg
```

- `arma3server_x64.exe`：可從 Arma 3 安裝資料夾複製
- `steam_appid.txt`：內容僅需為 `107410`

---

## 📦 2. 放置模組與金鑰

### 🔸 mods/
將 TF101 測試任務所需模組放入此資料夾，例如：

```
mods/
├── @ace
├── @rhsusaf
├── @ALiVE
...
```

### 🔸 keys/
確保每個模組內 `addons/` 中的 `.bikey` 金鑰也複製至 `keys/` 內，以便驗證模組完整性。

---

## 🎯 3. 放置任務 `.pbo`

將測試用任務封包（`.pbo`）放置於 `MPMissions/` 資料夾下：

```
MPMissions/
├── OP_Kamdesh_v0.1.lythium.pbo
├── mission_1_ALIVE_TF101.lythium.pbo
...
```

---

## ⚙️ 4. 建立 server.cfg 設定檔（基礎）

以下為 TF101 LAN 測試預設建議值：

```cfg
hostname = "TF101 Dev Server";
maxPlayers = 10;
password = "tf101test";
verifySignatures = 2;
voteThreshold = 1;
persistent = 1;
kickDuplicate = 1;
```

---

## 🚀 5. 建立啟動器（.bat 檔）

建立 `start_server.bat`，內容如下：

```bat
arma3server_x64.exe ^
-config=server.cfg ^
-port=2302 ^
-mod=@ace;@rhsusaf;@ALiVE;... ^
-name=TF101 ^
-enableHT
```

> 可依任務模組實際調整 `-mod=` 參數順序。

---

## 🧪 6. 啟動測試

1. 執行 `start_server.bat`
2. 開啟 Arma 3，從 LAN 加入伺服器
3. 測試 ALiVE / Simplex 生成是否正常

---

## 📘 備註建議

- 建議使用虛擬網卡或 Hamachi 做跨機 LAN 測試（若主機與玩家不同）
- 測試完畢可透過 log 檔確認是否載入成功

---

TF101 測試環境設定完成 ✅
如需 HC 架構請搭配 `TF101_HC_Deploy_Guide.md` 使用。
