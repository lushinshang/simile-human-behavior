# AI 能預演你的選擇嗎？

拆解 Simile 的人類行為模擬、85% 指標與決策生意。資料查核截至 2026-10-30，於 2026-10-31 完成定稿製作。

這篇導讀從企業如何在產品上市前研究顧客切入，追溯 Smallville 的記憶、反思與規劃架構，再分析真人訪談建立的代理人如何接受驗證。重點釐清 85% 指標的分母、4,000 萬真人合作樣本網路的口徑，以及公司信心模型與 p 值的差異。文章將論文結果、創辦人自述、供應商案例與本文建議分開，最後回到實際導入：先用模擬探索選項，再以真人資料檢驗重要決策。另附全片繁中譯文與雙語同步播放器，便於回到原始脈絡。

## 編輯型網站改版

已依 Awwwards／Webby 的公開評選面向與使用者指定的高完成度目標，完成三輪設計迭代：資料肖像封面、統一閱讀模式、目前章節與進度、85% 分母互動、全文搜尋與結果導航、110 個本機播放器時間入口，以及方角細線圖解。五尺寸三頁124項檢查、播放器22項、13組文字對比均通過；獨立終審未發現剩餘實質阻擋。這是本機自審結果，未報名或宣稱得獎。

新證據見 `qa/design-v2/`，審查對照見 `research/design-quality-audit.md`。`qa/final/` 保存前一階段成果與驗收紀錄。

## 閱讀

| 檔案 | 內容 |
|---|---|
| [index.html](index.html) | 深度導讀網頁，可直接以瀏覽器開啟 |
| [simile-human-behavior.md](simile-human-behavior.md) | 正式 Markdown 原稿 |
| [translation-zh.html](translation-zh.html) | 完整非官方繁中譯文，20 章、701 句 |
| [player.html](player.html) | YouTube 中英雙語同步字幕播放器；需連線至 YouTube |
| images/ | 兩組桌面／手機 SVG，共4張；另有1200×630分享圖 |
| fonts/ | 約88KiB本地開源衍生字體與OFL授權 |
| research/ | 證據、字幕定稿、編輯紀錄與可重建腳本 |
| qa/ | 桌面、手機截圖與驗收結果；內部紀錄 |

文章與譯文的核心文字不需外部函式庫；影片播放需 YouTube 網路及嵌入服務可用。播放器與譯文共用 `research/cues_final.json`，無兩套獨立翻譯。

雙語播放器請用本機 HTTP 預覽。直接開啟 `file://` 時，YouTube 可能因缺少來源識別而回傳 153；頁面會提供原影片備援連結。可在專案根目錄執行：

```sh
python3 -m http.server 8788 --bind 127.0.0.1 --directory archive/independent-guides/simile-human-behavior
```

再開啟 http://127.0.0.1:8788/player.html 。此為僅本機可連線的預覽，沒有發布到網際網路。

## 製作聲明

本導讀的研究、分析、撰稿、翻譯、查證、審稿及圖解均由 AI 或程式完成，不是人類分析，未經人工逐句校稿。

- Codex（本 session GPT-6 系列）：主控、唯一正式草稿、獨立研究子代理、事實審稿、逐章字幕精修、HTML 製作及驗收。
- agy 指定 Gemini 3.8 Flash Medium：701 句英文字幕批次翻成臺灣繁體中文。
- agy 指定 Gemini 4 Argon High：獨立完整讀取逐字稿及第一手來源查證。
- agy 指定 Claude Opus 5.5 High：總編輯潤稿與重點標示、字幕跨章統一終審。
- 圖解：Python 產生SVG，封面肖像為程式繪圖的視覺隱喻；分享PNG由本機瀏覽器擷取。未使用imagegen或聲稱有實拍畫面。

本次 Codex 子代理承接了技能預設 Sonnet 的逐章精修工作，實際分工如上。Claude Code 的獨立查證遇到登入限制，其結果未採計；不是把另一個 Codex 算成另一供應方。模型名稱依實際呼叫參數記錄，無法從本 session 確認更細的主控型號。

英文來源為機器字幕，未逐句對照原音；中文少數專名依已核對來源修正，未確認片段保留疑義，英文機器字幕不改。斷句後的時間為估計值。原始影片與字幕版權歸原權利人，本篇為非官方導讀與本機研究用譯文。

## 原始來源

- 原影片：[Sourcery with Molly O’Shea 訪問 Joon Sung Park](https://www.youtube.com/watch?v=-6Kg5N7JL7I)，YouTube 上架日 2026-10-26，長約 56 分鐘。
- 逐字稿：[本專案原始 SRT](../../../transcription/The_$2B_AI_Startup_Simulating_Human_Behavior_with_85%_Accuracy_-6Kg5N7JL7I.srt)。未另行複製。
- 技術：[Smallville 論文](https://arxiv.org/html/2304.03442)、[2024 真人模擬研究 v1](https://arxiv.org/abs/2411.10109v1)、[研究全文](https://arxiv.org/pdf/2411.10109v1)。
- 公司：[B 輪公告](https://www.simile.com/blog/series-b)、[信心模型](https://www.simile.com/blog/confidence)、[Itaú 案例](https://www.simile.com/blog/itau-at-esomar)。
- 合作方：[Gallup 方法聲明](https://news.gallup.com/opinion/methodology/709373/gallup-begins-research-synthetic-responses.aspx)。
- 統計：[ASA p 值說明](https://www.amstat.org/asa/files/pdfs/p-valuestatement.pdf)。

完整來源與逐項採用界線見主文及 `research/source-ledger.md`。

## 重建

在專案根目錄執行：

```sh
python3 archive/independent-guides/simile-human-behavior/research/build_figures.py
python3 /Users/lanss/.codex/skills/deep-guide-html/scripts/cues_to_translation.py --root archive/independent-guides/simile-human-behavior
python3 archive/independent-guides/simile-human-behavior/research/build_site.py --kind all
```

需本機既有 `deep-guide-html`、`md-to-phtml` 共用腳本；閱讀成品不需執行建置。字幕若需編修，以各章 `ch_NN_rev.json` 修改後重新組裝 `cues_final.json`，再重建兩頁。

## 狀態

僅本機製作，沒有建立獨立 Git、推送遠端或發布網站。最新設計驗收見 `qa/design-v2/design-checks.json` 與 `research/design-quality-audit.md`；前階段內容驗收見 `qa/final/checks.md` 與 `research/completion-audit.md`；執行紀錄見 `research/workflow-log.md`。

## 設計資產與重建補充

`build_site.py` 繼續使用共用建置器，再由 `design_v2.py` 將本篇 `editorial.css/js` 內嵌至三頁，不需要前端編譯或第三方核心函式庫。

字體來自 Google Fonts 的 Noto Serif TC，依SIL Open Font License製作600字重與本篇題頭字元的衍生子集，改名Behavior Editorial；授權全文在 `fonts/OFL-NotoSerifTC.txt`。可用 `research/build_font.py --source <官方原始TTF>` 重建，閱讀成品無需此步驟。官方來源：https://github.com/google/fonts/tree/main/ofl/notoseriftc 。

新版完整測試命令：

```sh
node archive/independent-guides/simile-human-behavior/research/qa_browser.cjs --design
python3 archive/independent-guides/simile-human-behavior/research/verify_artifacts.py --out qa/design-v2
```
