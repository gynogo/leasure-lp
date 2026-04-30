# 屋主開發頁｜工作交接文件
> 下次開始時，對 Claude Code 說：「讀取包租代管/屋主招募/LP/_ai_handoff.md，繼續工作。」
> 最後更新：2026-05-01（Step 4 精修完成，準備 Step 5 部署）

---

## 專案概述

為 Gyno 包租代管事業製作一頁式 landing page，目標受眾為雙北 45 歲以上屋主。
核心 CTA：Line 預約免費到府評估。
品牌名稱：**租逸**｜公司：居室生活有限公司

---

## 本專案文件

| 檔案 | 用途 |
|---|---|
| `01_企劃主文件.md` | 策略層，區塊順序與溝通目標 |
| `02_文案文件.md` | 純文案，所有區塊實際文字 |
| `03_設計企劃.md` | 視覺概念 + 手機版排版規格 |
| `_ai_handoff.md` | 本文件，工作進度與下一步 |

**事業體共用資源：** `../包租代管/_context.md`

---

## 已確認的內容決策

- 信任錨點：德國紅點設計獎、30+ 房客、近半數外商或海外背景
- 屋主見證：民生社區羅太太、信義區王先生、景美林先生
- 試算數據：一般住宅 6,000 元/月免稅 + 53% 扣除（公益出租人）
- **LINE 帳號：個人帳號 `ginoboya`，URL：`https://line.me/ti/p/~ginoboya`**
- 計算器：內嵌在 landing page（非 iframe）

---

## ✅ Step 4 完成｜HTML Prototype 精修完畢

### 生成檔案
- `index.html` — 完整 10 個區塊 Landing Page
- `style.css` — 設計系統 CSS，含 design tokens
- `img/` — 實際照片資料夾（部分仍為紅色佔位）

### 本次精修內容（2026-04-30 至 2026-05-01）

**試算區塊**
- 長條圖差額方塊：改為**紅色斜線**疊在灰色（自行申報）長條頂端，採用損失框架心理學
- Hover tooltip：「每年多繳 NT$ X,XXX」
- 自行申報金額：紅色字

**地價稅/房屋稅區塊**
- 標題：「不只所得稅，地價稅和房屋稅最高更能省到 80%」
- 右欄（包租代管）加金色頂線 + 藍色說明文字 + 金色「省 80%」「省 60–75%」badge
- 新增 CTA：「預約免費評估，不再多繳稅 ↗」

**首圖（Hero）**
- 大標放大：`clamp(38px, 10vw, 60px)`
- Nav 品牌字「租逸」：15px → 20px
- Nav CTA：「免費評估」（捲到頁底）
- 下方副標：改回 Regular 字重（層級：粗體定位 → 明體大標 → 細字補充）
- 手機版按鈕：修正全寬問題（`align-items: flex-start`）

**CTA 按鈕**
- 全部箭頭統一換為 ↗
- 四顆主要按鈕 → 直接開 LINE（`https://line.me/ti/p/~ginoboya`）
- FAQ「先預約看看也無妨 ↗」→ 直接開 LINE
- Nav「免費評估」→ 捲到頁底 CTA 區塊
- 新增兩顆按鈕：見證區後（「我也想聊聊我的房子 ↗」）、試算區後

**前後對比照片**
- 翻修前/後標籤移至兩張照片**中央交界處**

**比較表**
- 「交給包租代管」欄：藍底白 ✓ 圓圈（CSS `::before`）

**見證區**
- 三則見證文案更新
- 關鍵詞粗體藍字（`.hl` class）

**環境趨勢區塊（新聞來源）**
- 三張卡片各加來源連結（Chip 樣式 + 🔗 emoji）
- 內政部 / 樂屋網 / 好房網

**案例照片插入**
- 流程之後：`img/jm_casestudy.jpg`（2:1 全出血）
- FAQ 之後：`img/xd_intimate.jpg`（3:2 全出血）

**FAQ**
- 全部 8 題問答更新為最新版本

**Footer**
- 「租逸相信」+ 「愈租，屋愈好；愈租，人愈逸。」
- 電話 (02)6605-7271、服務區域
- COPYRIGHT © 2026. ALL RIGHTS RESERVED.

---

## 本機預覽

```
cd 包租代管/屋主招募/LP && python3 -m http.server 8765
```
開啟 `http://localhost:8765/index.html`

---

## ⏭️ 下一步：Step 5｜部署至 GitHub Pages

### 準備動作（下次開始前）

**第一步：建立 GitHub Repository**
1. 前往 `github.com` → New Repository
2. 命名建議：`zuyi-lp`（或 `租逸-lp`）
3. 設為 **Public**（GitHub Pages 免費版需 Public）
4. 不要勾選 Initialize README

**第二步：推送本地檔案**
在 LP 資料夾執行：
```bash
git init
git add .
git commit -m "init: 租逸屋主招募 LP"
git branch -M main
git remote add origin https://github.com/[你的帳號]/zuyi-lp.git
git push -u origin main
```

**第三步：開啟 GitHub Pages**
- Repository → Settings → Pages
- Source 選 `main` branch，根目錄 `/`
- 儲存後取得網址（約 1–2 分鐘生效）

**第四步：更新 LINE 按鈕**
- 確認部署後所有 LINE 連結正常跳轉
- 日後如換 LINE Official Account，全域搜尋 `ginoboya` 一次替換

---

## 上線前待確認清單

| 項目 | 狀態 |
|---|---|
| Hero 背景照 `img/hero_xsroomc.jpg` | ✅ 已有 |
| 案例照 `img/jm_casestudy.jpg` | 待確認有無檔案 |
| 案例照 `img/xd_intimate.jpg` | 待確認有無檔案 |
| 其他紅色佔位照片 | 待替換 |
| LINE 帳號（建議申請 Official Account） | 目前使用個人帳號 |
| 公司電話 (02)6605-7271 | ✅ 已填入 |
| 三個來源連結可否正常開啟 | 待點擊確認 |
