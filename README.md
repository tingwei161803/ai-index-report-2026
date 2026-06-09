# AI 指數報告 2026 · AI Index Report 2026

> 把史丹佛 HAI 長達 425 頁的《人工智慧指數報告 2026》,整理成一頁可互動、可中英切換的編輯式網站。

這是史丹佛以人為本 AI 研究院(Stanford HAI)第九版《Artificial Intelligence Index Report 2026》的**非官方教育性重新整理**:把報告的「15 條重點摘要」「9 大章節亮點」與幾組關鍵數據,做成一個零建置、純靜態、可上線分享的單頁網站。每個數字都直接取自報告原文。

---

## 🔗 線上版 / Live

| | |
|---|---|
| 🌐 網站 | <https://ai-index-report-2026.peteraim.com/> |

> 直接點進去就能用,無需安裝。可用 `https://ai-index-report-2026.peteraim.com/#<slug>` 深連結到特定重點(例如 `#us-china-gap-closed`)。

---

## ✨ 功能特色

- 🌏 **中英文全頁切換** — 一鍵把整頁(卡片、章節、圖表、導覽、標題)切換為中文 / English,無任何殘留
- 🌗 **深色 / 淺色模式** — 暖色調學術風,手動切換並記憶於 `localStorage`
- 🧭 **複合多區段 + 黏著式導覽** — Hero → 15 條重點 → 9 大章節 → 美中對比 → 數據圖表 → 名言 → 來源,捲動時自動高亮所在區段(scrollspy)
- 🃏 **15 條重點卡片 + 詳情對話框** — 點任一張(編號 01–15)展開完整結論與數字
- 📚 **九大章節詳解頁** — 每一章都有獨立深入頁(研發、技術表現、負責任 AI、經濟、科學、醫療、教育、政策與治理、民意),含 Hero 數字、分區段說明、多組圖表、子趨勢卡片;從 appbar「章節」與主頁各章節展開的「完整詳解 →」皆可進入,頁底並有「上一章 / 所有章節 / 下一章」導覽
- 📊 **大量內嵌 SVG 圖表** — 投資、採用率、事故、運算、FDA 醫材、發表成長、專家 vs 大眾⋯⋯約 30+ 組圖表,無圖表函式庫
- 🔗 **深連結** — 每條重點都有專屬 `#<slug>`,可直接分享
- 🎞️ **進場微動效** — 區塊捲入時輕柔淡入(尊重 `prefers-reduced-motion`)
- 📱 **響應式設計** — 手機、平板、桌機皆適配,375px 無水平溢出
- 🔎 **SEO / OG / JSON-LD** — 具備社群預覽與結構化資料
- ⚡ **純靜態零建置** — 無後端、無打包工具、載入快、可離線瀏覽

---

## 📂 內容結構 / 資料來源

本站內容整理自 **史丹佛 HAI《Artificial Intelligence Index Report 2026》(第九版)**。

```
ai-index-report-2026/
├── docs/                 # 網站本體(GitHub Pages 從此資料夾發布)
│   ├── index.html        # 入口頁:總覽 + 15 重點 + 9 章節 + 圖表
│   ├── research.html / performance.html / responsible-ai.html / economy.html
│   ├── science.html / medicine.html / education.html / policy.html / public-opinion.html
│   │                     # ↑ 九大章節詳解頁(全部共用同一套 app.js / styles.css)
│   ├── data/
│   │   ├── data.js        # 主頁資料層:SITE_META + SITE_SECTIONS(雙語 {en, zh})
│   │   └── <chapter>.js   # 各章節資料層(research.js … public-opinion.js,雙語)
│   ├── assets/
│   │   ├── styles.css     # 編輯/極簡學術風(暖色單色 + 黏土色強調)
│   │   └── app.js         # 區段渲染、i18n、主題、對話框、捲動動效、跨章節導覽(全站共用)
│   └── .nojekyll          # 讓 Pages 略過 Jekyll
├── ai_index_report_2026.pdf   # 原始報告 PDF(資料來源)
└── README.md
```

**資料來源(官方):**

- 報告主頁:<https://hai.stanford.edu/ai-index/2026-ai-index-report>
- 完整 PDF:<https://hai.stanford.edu/assets/files/ai_index_report_2026.pdf>

**視覺靈感**(僅取靈感、未照抄):編輯式資料新聞 [The Pudding](https://pudding.cool/)、簡潔圖表美學 [Datawrapper](https://www.datawrapper.de/)。

> ⚠️ **非官方**:本網站為個人整理之非官方資源,內容整理自上述報告,數字多為估計值且基準持續變動,如有錯誤或出入,**請以官方來源為準**。

---

## 🛠 本機使用

```bash
# 1. clone 專案
git clone https://github.com/tingwei161803/ai-index-report-2026.git
cd ai-index-report-2026

# 2a. 最簡單:直接開啟入口頁
open docs/index.html

# 2b. 或啟動本機伺服器(建議,深連結才正常)
uv run python -m http.server 4173 --directory docs
# 然後瀏覽 http://localhost:4173
```

> 本專案為純靜態網站,不需安裝任何依賴。若要跑本機伺服器,一律使用 `uv`。

### (選配)用 Playwright 驗收

```bash
uv run --with playwright playwright install chromium     # 首次
uv run --with playwright python <skill>/scripts/verify.py --dir docs
```

---

## 📝 聲明 / License

- 本站為**非官方**整理;報告內容著作權歸 **Stanford University** 所有,原報告以 **CC BY-ND 4.0** 授權。
- 本網站的程式碼以 **MIT** 授權釋出。
- 引用報告請依官方格式:*"The AI Index 2026 Annual Report," AI Index Steering Committee, Stanford HAI, April 2026.*
- 如為權利人且希望調整或移除內容,請開 issue 聯絡。
