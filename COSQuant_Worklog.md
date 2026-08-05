# COSQuant 審稿 Worklog

參照 EMNLP_Demo_Review_SOP.md 的步驟進度紀錄。

## 2026-08-01

### 完成的步驟
- 步驟1(確認審稿標準):查證 EMNLP 2026 demo track 官方CFP,確認評分維度與今年新規則(必須有評估、必須有demo影片+live連結)。
- 步驟2(粗讀):讀完 abstract、introduction、conclusion、limitations,建立整體印象。
- 步驟3(精讀):讀完 Section 2(2.1資料策劃、2.2演算法整合、2.3部署評估、2.4模組化設計)+ Section 3(3.1實驗設定、3.2三段結果:PTQ組合實驗、QAT組合實驗、資料策劃實驗)。
- 步驟4(Claim check):邊讀邊做,逐項核對數據支撐主張的程度。
- 步驟5(可重現性檢查):看過 demo影片(118秒)+ GitHub repo(Cfish808/LLM-Compression-Tool)README。

### 關鍵發現

**Demo可用性疑慮(步驟5)**
- Demo影片118秒中,約100秒都是終端機執行畫面(pip install / 跑指令的log與進度條),前12秒是滾動README,全片無GUI、無互動畫面。
- GitHub Usage說明證實:操作方式完全是「改YAML設定檔 + 下指令執行」(`python main.py --config config/llama_gptq.yml`),沒有網頁介面或API server。
- 沒有 user study / human evaluation,不符合CFP明確要求的評估項目。
- 所有實驗結果都是單次執行的point estimate,無信賴區間或顯著性檢定。
- 判斷:形式上符合demo track「software tool for NLP research」類別,但可展示性/互動性偏弱,更像工具論文而非系統demo。

**Table 4 數據錯誤(嚴重,已用兩種方法交叉驗證)**
- Qwen3-8B 的 GPTQ 2-bit 那一列(2個perplexity + 5個zero-shot準確率)與 Llama2-7B 對應列完全相同,判斷為複製貼上錯誤。
- 另外三列(sparsegpt+gptq、wanda+gptq、magnitude+gptq)的 Avg 欄位,與該列自身逐項分數重新計算後不符,但精準對應到 Llama2-7B 對應列的 Avg。
- 直接影響論文核心主張:「組合壓縮策略的優勢可跨模型架構(LLaMA、Qwen)泛化」。

**Table 5 表述問題(中等)**
- 論文稱蒸餾讓 EfficientQAT* 進步「約1%」,但逐項核對:Hellaswag任務蒸餾版反而退步0.06%,平均數字掩蓋了這個例外。
- 查證全文(Results、Limitations)均未提及或解釋此退步。

**Table 6 過度概括(輕微)**
- 「C4對推理任務加成最明顯」只在4-bit成立,3-bit時其實是知識類任務增益最大。
- 「COLA特別在推理任務贏很多」只在3-bit成立,4-bit時COLA在三類任務上的優勢分布均勻,推理不特別突出。
- 「低位元時資料優化效果更明顯」幾乎完全由推理任務單獨撐起,常識/知識任務看不出此規律。
- 建議措辭:論述有過度概括之嫌,未清楚區分3-bit與4-bit的模式差異(避免直接指控刻意造假)。

### 待完成
- 步驟6:整理優缺點清單(Strengths and Weaknesses)
- 步驟7:正式寫review(對照 Google Doc「EMNLP Demo Review」COSQuant分頁的官方review表單格式)

### 下次接續
從步驟6開始,把以上發現整理成正式的 Strengths/Weaknesses 清單。
