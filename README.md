# MathSnap 官方網站

MathSnap 是一款 macOS menubar app，按下快捷鍵框選截圖，自動將數學公式轉成 LaTeX 並複製到剪貼板。

本 repo 為 MathSnap 的官方靜態網站，部署於 GitHub Pages。

## 頁面

| 檔案 | 說明 |
|------|------|
| `index.html` | 首頁 Landing Page |
| `support.html` | 支援中心（FAQ + 快速開始） |
| `privacy.html` | 隱私權政策 |

## 本地預覽

### 方法一：VS Code Live Server（推薦）

1. 安裝 VS Code 擴充功能 [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
2. 在 VS Code 開啟本資料夾
3. 右鍵點擊 `index.html` → **Open with Live Server**
4. 瀏覽器自動開啟 `http://127.0.0.1:5500`

### 方法二：Python 內建伺服器

```bash
# Python 3
cd mathsnap-site
python3 -m http.server 8080
```

開啟瀏覽器前往 `http://localhost:8080`

### 方法三：直接開啟檔案

直接在 Finder 雙擊 `index.html` 以預設瀏覽器開啟。
注意：部分瀏覽器對 `file://` 協議有限制，建議使用上述伺服器方式。

## 部署到 GitHub Pages

### 首次部署

1. 在 GitHub 建立新的 repository（例如 `mathsnap-site`）

2. 將本地檔案推上 GitHub：
   ```bash
   cd mathsnap-site
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/你的帳號/mathsnap-site.git
   git push -u origin main
   ```

3. 前往 GitHub repo 頁面 → **Settings** → **Pages**

4. Source 選擇 **Deploy from a branch**，Branch 選 `main`，資料夾選 `/ (root)`

5. 點擊 **Save**，等待約 1 分鐘後網站即可透過以下網址存取：
   ```
   https://你的帳號.github.io/mathsnap-site/
   ```

### 後續更新

```bash
git add .
git commit -m "Update content"
git push
```

推送後 GitHub Actions 自動重新部署，約 1 分鐘生效。

## 技術規格

- 純 HTML + CSS + Vanilla JavaScript，無任何框架或建置工具
- 字型：[Inter](https://fonts.google.com/specimen/Inter)（Google Fonts）
- 支援 RWD（手機 / 桌機）
- 部署：GitHub Pages，無需任何 build step

## 待辦事項

部署前記得更新：

- [ ] 所有頁面的 Download 按鈕 `href="#download"` → 替換為 App Store 或實際下載連結
- [ ] `support.html` 和 `privacy.html` 的 `mailto:` → 填入實際 email 地址
- [ ] `index.html` 的 `og:image` → 加入社群分享預覽圖
