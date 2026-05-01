# 屋主開發頁｜工作交接文件
> 下次開始時，對 Claude Code 說：「讀取包租代管/屋主招募/LP/_ai_handoff.md，繼續工作。」
> 最後更新：2026-05-01（Step 5 部署完成，LP 已上線）

---

## 專案概述

為 Gyno 包租代管事業製作一頁式 landing page，目標受眾為雙北 45 歲以上屋主。
核心 CTA：Line 預約免費到府評估。
品牌名稱：**租逸**｜品牌英文名：**Leasure**｜公司：居室生活有限公司

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

## ✅ Step 5 完成｜已部署至 GitHub Pages

### 部署資訊

| 項目 | 內容 |
|---|---|
| 線上網址 | `https://gynogo.github.io/leasure-lp/` |
| GitHub Repo | `https://github.com/gynogo/leasure-lp` |
| GitHub 帳號 | `gynogo`（使用 ginoboya@gmail.com 登入） |
| Branch | `main` |
| 部署方式 | GitHub Pages（Source: main, 根目錄）|

### 本次完成內容（2026-05-01）

**部署與環境**
- 安裝 GitHub CLI（`gh`），完成 OAuth 登入
- 建立 repo `leasure-lp`，推送所有檔案，開啟 GitHub Pages
- 建立 `_workspace/` 暫存資料夾，更新 `.gitignore`，CLAUDE.md 新增臨時檔案規則

**資料夾整理**
- 刪除根目錄與 LP 資料夾的所有開發截圖（共 38 個）
- `prototype/` 移至 `包租代管/archive/屋主招募_prototype/`
- 保留 `preview_full_hq.png` 作為視覺紀錄

**Meta / SEO**
- `<title>`：`租逸｜得獎設計師的包租代管｜雙北`
- `og:title`：同上
- `og:description`：雙北老屋交給得獎設計師，零前期成本翻修，每月穩定收租，稅務全包辦。免費到府評估。
- `og:image`：Hero 首圖 `img/hero_xsroomc.jpg`
- LINE Card Validator 可強制刷新預覽

**手機版修正**
- 前後照片 Carousel touch 事件改綁在容器（`#ba-slider`），修正滑到第二張後無法繼續滑的問題
- 加入方向判斷：垂直滑捲頁，水平滑換張

**文案更新**
- 計算器區塊標題：`合法出租，租金收入所得稅其實更省`
- 地價稅房屋稅區塊標題：`合法出租，地價稅與房屋稅最高可省 80%`
- 最壞情境標籤：`未申報出租最壞情境（以追溯 5 年為例）`
- 最壞情境說明：`補稅 + 罰鍰 3 倍 + 滯納金 15%｜尚不含地價稅、房屋稅補繳差額——實際總額只會更高。`
- 最壞情境顯示格式：`NT$ X,XXX +`

**計算器公式更新**
- 舊：`tSelf × 5 × 1.5`（5年 × 1.5倍）
- 新：`tSelf × 5 × 4.15`（5年 × 補稅1 + 罰鍰3倍 + 滯納金15%）
- 以月租 $30,000、稅率 20% 為例，最壞情境：NT$ 851,580 +

**設計調整**
- 環境趨勢卡片「來源」連結：改為藍色空心框 pill 按鈕，加 `box-shadow` 浮起感、`:hover` 填色、`:active` 填色（手機觸控回饋）
- 環境趨勢卡片「分類標籤」：加 `border-radius: 4px`、`cursor: default`，與按鈕形成小方角 vs 大圓角的視覺對比

---

## 本機預覽

```
cd 包租代管/屋主招募/LP && python3 -m http.server 8765
```
開啟 `http://localhost:8765/index.html`

---

## 上線確認清單

| 項目 | 狀態 |
|---|---|
| 所有照片（Hero + before/after + 案例） | ✅ 13 張全數到位 |
| 紅色佔位框 `.photo-ph` | ✅ HTML 中完全未使用 |
| LINE 連結（5 顆按鈕） | ✅ 全部指向 `line.me/ti/p/~ginoboya` |
| 公司電話 (02)6605-7271 | ✅ 已填入 |
| 三個來源連結 | ✅ 已嵌入，建議手動點擊確認可開啟 |
| GitHub Pages 部署 | ✅ 已上線 |

---

## 待辦（有需要再做）

| 項目 | 優先級 | 說明 |
|---|---|---|
| 自訂網域 | 低 | 買 `leasure.com.tw` 或類似，目前 github.io 可先用 |
| LINE Official Account | 低 | 目前使用個人帳號，建議申請正式帳號後全域替換 `ginoboya` |
| git 作者資訊設定 | 低 | 每次 commit 提示未設定 name/email，可執行 `git config --global user.name "Gyno"` 等 |
