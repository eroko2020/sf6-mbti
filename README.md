# SF6 MBTI 測試頁面 — 網站部署指南

## 檔案結構

```
deploy-web/
├── sf6-mbti.html       # 主頁面（已就緒）
├── sf6-chars/           # 19張角色立繪 PNG
│   ├── ryu.png
│   ├── chunli.png
│   └── ...
└── README.md
```

## 部署方式

### 方式一：GitHub Pages（推薦，免費）

1. 在 GitHub 建立一個新的 Repository（例如 `sf6-mbti`）
2. 將整個 `deploy-web/` 目錄內容上傳到 Repository 根目錄
3. 進入 Repository → Settings → Pages
4. Source 選擇 `main` 分支，點 Save
5. 等待 1-2 分鐘，獲得公開網址：`https://你的帳號.github.io/sf6-mbti/sf6-mbti.html`

```bash
# 或在終端機中執行：
cd deploy-web
git init
git add .
git commit -m "SF6 MBTI Test"
git branch -M main
git remote add origin https://github.com/你的帳號/你的repo.git
git push -u origin main
```

### 方式二：騰訊雲 COS 靜態網站

1. 登錄 [騰訊雲 COS 控制台](https://console.cloud.tencent.com/cos)
2. 建立 Bucket（公有讀、靜態網站模式）
3. 上傳 `deploy-web/` 內所有檔案到 Bucket 根目錄
4. 設定靜態網站索引文件為 `sf6-mbti.html`
5. 獲得訪問網址（可綁定自定義域名 + CDN 加速）

### 方式三：任意靜態託管服務

支援任何靜態網站託管（Netlify / Vercel / Cloudflare Pages / 騰訊雲 CloudBase 等），根目錄設定為 `deploy-web/`，入口文件為 `sf6-mbti.html`。

---

## 本地預覽

```bash
cd deploy-web
python -m http.server 8080
# 打開 http://localhost:8080/sf6-mbti.html
```
