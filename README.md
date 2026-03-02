# 🍳 早餐點餐計算器 PWA

手機版早餐店點餐金額計算器，支援完全離線使用。

**Live Demo:** `https://<你的帳號>.github.io/<repo名稱>/`

---

## 📁 專案結構

```
/
├── index.html          # 主程式（HTML + CSS + JS 全合一）
├── menu.json           # 菜單資料
├── manifest.json       # PWA 設定檔
├── service-worker.js   # 離線快取 Service Worker
├── README.md           # 本文件
└── icons/
    ├── icon-192.png        # Android 主畫面圖示
    ├── icon-512.png        # 高解析度圖示
    └── apple-touch-icon.png # iPhone 主畫面圖示
```

---

## 🚀 部署到 GitHub Pages（5 分鐘完成）

### 方法一：網頁介面上傳（推薦新手）

**Step 1 — 建立 Repository**

1. 登入 [github.com](https://github.com)
2. 右上角點 **＋ → New repository**
3. Repository name 填入：`breakfast-order`（或任意名稱）
4. 選 **Public**（Private 無法免費啟用 Pages）
5. 勾選 **Add a README file**
6. 點 **Create repository**

**Step 2 — 上傳檔案**

1. 在 repository 頁面點 **Add file → Upload files**
2. 將以下檔案／資料夾全部拖入上傳區：
   - `index.html`
   - `menu.json`
   - `manifest.json`
   - `service-worker.js`
   - `icons/`（整個資料夾）
3. 點 **Commit changes**

**Step 3 — 開啟 GitHub Pages**

1. 點上方 **Settings** 分頁
2. 左側選單點 **Pages**
3. Source 選 **Deploy from a branch**
4. Branch 選 **main**，資料夾選 **/ (root)**
5. 點 **Save**
6. 等待約 1～2 分鐘，頁面上方會出現：
   > ✅ Your site is live at `https://<帳號>.github.io/breakfast-order/`

---

### 方法二：Git 指令（熟悉 CLI 者）

```bash
git clone https://github.com/<你的帳號>/breakfast-order.git
cd breakfast-order

# 複製所有專案檔案進來
cp -r /path/to/pwa-breakfast/* .

git add .
git commit -m "deploy PWA breakfast app"
git push origin main
```

然後同 Step 3 開啟 Pages 即可。

---

## 📱 iPhone 加入主畫面教學

> 加入後會像原生 App 一樣全螢幕開啟，沒有瀏覽器網址列。

**Step 1** — 用 **Safari** 開啟你的 GitHub Pages 網址
（必須用 Safari，Chrome/Firefox 不支援 iOS 安裝 PWA）

**Step 2** — 點下方工具列的 **分享按鈕**（方框加箭頭 ↑）

**Step 3** — 在選單中滑動找到 **「加入主畫面」**，點它

**Step 4** — 確認名稱為「早餐點餐」，點右上角 **「新增」**

完成！桌面上會出現橘色煎蛋圖示，點開後全螢幕運作，**離線也能使用**。

---

## ✅ PWA 功能說明

| 功能 | 說明 |
|------|------|
| 離線使用 | 首次開啟後自動快取，之後無網路也能正常點餐 |
| 加入主畫面 | iOS Safari / Android Chrome 皆支援 |
| 全螢幕模式 | 無瀏覽器工具列，像原生 App |
| 訂單記憶 | localStorage 儲存點餐狀態，重開不歸零 |
| 離線提示 | 斷線時 Header 顯示「離線模式」提示 |

---

## 🔧 更新菜單

直接編輯 `menu.json`，格式如下：

```json
{
  "name": "品項名稱",
  "price": 30,
  "category": "分類名稱",
  "options": [
    { "name": "規格1", "price": 30 },
    { "name": "規格2", "price": 35 }
  ]
}
```

修改後 push 到 GitHub，GitHub Pages 自動更新。用戶下次開啟時 Service Worker 會在背景拉取新版本。
