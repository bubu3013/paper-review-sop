# EMNLP Demo Track 審稿 SOP

## 1. 確認 venue 審稿標準
先看 EMNLP demo track 的評分表單/CFP，弄清楚評分維度：novelty、technical soundness、clarity、demo 可用性、可重現性。同時記住 demo paper 的核心期待：系統是否真的可用、展示是否清楚、互動是否順暢、對社群是否有實際價值（不只是 novelty）。

### EMNLP 2026 Demo Track 官方標準（來源：https://2026.emnlp.org/calls/demos/）

審稿制度：single-blind（作者資訊不隱藏），無 rebuttal 階段，審稿意見要一次寫到位。

論文需回答以下問題，這是審稿核心維度：
- 系統解決什麼問題
- 為什麼重要、影響力是什麼
- 方法/技術的新穎性
- 目標受眾是誰
- 系統如何運作
- 跟既有系統的比較
- 授權方式（license）
- 如何評估的（有沒有做 user study / human evaluation）

今年新規則（審稿時要特別檢查）：
- 沒有任何形式評估的投稿可能會被 desk reject，要確認論文有評估章節
- 必須附 demo 影片（最多 2.5 分鐘）+ live demo 連結或可安裝套件，缺少會被 desk reject（除非有正當理由，如需要特殊硬體）
- 篇幅上限 6 頁 + 不限頁數的 ethics/broader impact 聲明 + 不限頁數的 references，appendix 最多 2 頁

Ethics 要求符合 ACM Code of Ethics，若作者未妥善處理倫理疑慮可據此提出意見。

## 2. 粗讀一遍
先讀 abstract、intro、conclusion，抓整體方向與主張，先不評分不挑錯。

## 3. 精讀並記筆記
通讀全文，針對以下維度逐一記錄，並標註頁碼/段落方便之後寫 review：
- 貢獻是否清楚、是否新穎（與既有方法比較）
- 方法/系統設計是否合理，實驗設置是否足夠支撐論點
- Demo 本身：有沒有實際系統可操作、影片或截圖是否清楚展示功能
- 寫作清晰度、圖表是否易懂
- 是否有明顯遺漏的相關文獻

## 4. Claim check
把論文主要主張逐條列出，逐一核對是否有對應證據支持，避免漏掉誇大宣稱。

## 5. 可重現性檢查
拆細來看：有沒有 code/demo 影片、環境依賴是否清楚、部署難度如何、是否能在合理條件下重現 demo 效果。

## 6. 整理優缺點
列出 major strengths 與 major/minor weaknesses，每一點都要有具體依據。區分「會影響接受與否的問題」與「次要問題（語句、排版、圖表）」。若資訊不足無法判斷，標成「需作者澄清」，不要硬下結論。

## 7. 寫審稿意見
結構：一句話總結論文在做什麼 → major strengths → major weaknesses → questions for authors → minor issues（typo、格式）。語氣要建設性，即使拒稿也要說明原因與改進方向。

## 8. 打分與 confidence
依表單填 soundness/excitement/overall score，並誠實填寫 confidence。

## 9. 倫理檢查
確認是否有抄襲嫌疑、重複投稿、未聲明的利益衝突。
