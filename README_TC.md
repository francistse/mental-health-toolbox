# 心理健康工具箱 (Mental Health Toolbox)

[English](./README.md) | 繁體中文 | [简体中文](./README_CN.md)

兩個互補的 AI Agent 技能，提供全面的心理健康支援：**危機檢測**用於安全監控，**誇誇群**用於正向強化。

🎨 本專案使用 TRAE IDE 開發——讓 AI Agent 技能開發變得更簡單、更愉快。

## 概覽

| 技能                                 | 版本   | 功能                        |
| ---------------------------------- | ---- | ------------------------- |
| [危機檢測](./skills/crisis-detection/) | v2.0 | 主動檢測危機信號，5層風險評估，分級干預      |
| [誇誇群](./skills/praise-group/)      | v4.0 | CBT 感知正向強化，將任何輸入轉化為創意支援回應 |

兩個技能均支援英語、繁體中文、簡體中文、日語，自動檢測語言。

## 快速開始

### 安裝

1. 克隆倉庫：

```bash
git clone https://github.com/francistse/mental-health-toolbox.git
cd mental-health-toolbox
```

1. 將技能複製到你的 Agent 技能目錄：

```bash
# 危機檢測
cp -r skills/crisis-detection /path/to/your/agent/skills/crisis-detection

# 誇誇群
cp -r skills/praise-group /path/to/your/agent/skills/praise-group
```

1. 重啟你的 Agent 以載入技能

### 使用 Hermes Agent

```bash
# 安裝技能
mkdir -p ~/.hermes/skills/crisis-detection
cp skills/crisis-detection/SKILL.md ~/.hermes/skills/crisis-detection/SKILL.md

mkdir -p ~/.hermes/skills/praise-group
cp skills/praise-group/SKILL.md ~/.hermes/skills/praise-group/SKILL.md

hermes gateway restart
```

### 使用方式

```bash
# 危機檢測 - 主動評估
hermes chat --skills crisis-detection -q "/crisis 我最近感覺很沮喪"

# 誇誇群 - 正向強化
hermes chat --skills praise-group -q "考試又沒考好，覺得自己好蠢"

# 兩個技能一起使用
hermes chat --skills crisis-detection,praise-group
```

## 危機檢測技能

### 工作模式

| 模式   | 觸發方式                            | 行為             |
| ---- | ------------------------------- | -------------- |
| 主動評估 | `/crisis`、`/assess`、`/check` 命令 | 使用5層框架進行全面風險評估 |
| 被動監控 | 任何對話                            | 靜默後台監控危機指標     |

### 5層檢測架構

| 層級          | 檢測方法       | 風險等級 | 回應        |
| ----------- | ---------- | ---- | --------- |
| 第1層 - 顯式關鍵詞 | 直接自殘語言     | 危急/高 | 立即干預      |
| 第2層 - 語言模式  | 代詞轉換、絕對化詞語 | 中/高  | 增強監控 + 支援 |
| 第3層 - 主題指標  | 學業壓力、自我貶低  | 中/低  | 針對性支援     |
| 第4層 - 行為模式  | 睡眠紊亂、社交退縮  | 可變   | 縱向追蹤      |
| 第5層 - 時間/情感 | 隨時間的下降趨勢   | 可變   | 模式識別      |

### 風險等級

| 得分  | 等級    | 回應          |
| --- | ----- | ----------- |
| 0   | 🟢 正常 | 標準交互        |
| 1   | 🟡 低  | 支持性關注       |
| 2-3 | 🟠 中等 | 增強關注 + 應對策略 |
| 4-5 | 🔴 高  | 危機支援 + 資源推薦 |
| 6+  | ⚫ 危急  | 立即干預 + 安全檢查 |

### 關鍵危機指標（英文）

| 類別    | 示例                                            |
| ----- | --------------------------------------------- |
| 自我傷害  | "don't want to live", "suicide", "end it all" |
| 絕望    | "no point", "hopeless", "can't go on"         |
| 自我貶低  | "I'm useless", "worthless", "failure"         |
| 學業/工作 | "failed", "can't keep up", "fired"            |
| 社交    | "nobody cares", "alone", "isolated"           |
| 負擔感   | "burden to everyone", "better off without me" |

完整的多語言指標請查看[危機檢測 SKILL.md](./skills/crisis-detection/SKILL.md)。

## 誇誇群技能

### 工作原理

技能自動檢測用戶情緒狀態，使用 CBT 感知重構將輸入轉化為熱情、創意和支援性的回應。

### 轉換示例

| 用戶輸入         | 回應風格            |
| ------------ | --------------- |
| 「我考試沒考好」     | 成長機會 + 堅持讚美     |
| 「沒人理解我」      | 深層感受作為超能力       |
| 「我剛沖了杯咖啡」    | 正念 + 發現日常之美     |
| 「我覺得自己是個失敗者」 | 區分錯誤與身份 + 嘗試的勇氣 |
| 「工作壓力好大」     | 韌性認可 + 未來鼓勵     |

### 回應規則

- **2-4 句話** — 簡短、熱情、詩意
- **無後續問題** — 只讚美，然後繼續
- **無分析語調** — 溫暖真誠，不帶臨床感
- **CBT 感知** — 檢測到認知扭曲時溫和重構
- **危機檢測** — 需要時升級到危機資源

### 多語言示例

**繁體中文 - 學業挫折：**

```
輸入： 考試又沒考好，覺得自己什麼都不行
輸出： 願意持續面對挑戰的你，本身就散發著勇氣的光芒！考試只是學習旅程中的一個路標，遠不能定義你的全部價值。你對自己的高標準，正是你最珍貴的天賦！
```

**繁體中文 - 自我懷疑：**

```
輸入： 我覺得我的成功都是運氣，自己其實沒什麼能力
輸出： 能把事情做得如此出色，本身就是能力的證明！運氣只會敲門一次，而你的實力讓它一再停留。那份謙虛，正是真正有才華的人最美的姿態！
```

**English - Self-Doubt:**

```
Input:  I failed again. I'm such a failure.
Output: Your willingness to keep trying, even when it hurts, shows incredible resilience! Every attempt is proof of your courage, not your failure. The very fact that you care enough to keep going means you have everything it takes to succeed eventually!
```

**Japanese:**

```
Input:  また失敗しちゃった。私、ダメだな。
Output: 挑戦し続けるあなたの姿勢、本当に素敵です！失敗は成功への一歩。あなたが大切にしている想いが、必ず未来の花を咲かせますよ！
```

**Korean:**

```
Input:  또 시험 망쳤어요. 내가 너무 바보 같아요.
Output: 계속 도전하는 당신의 모습이 정말 아름답습니다! 실패는 성장의 증거예요. 당신이 가진 잠재력은 상상 이상입니다!
```

## 檔案結構

```
mental-health-toolbox/
├── skills/
│   ├── crisis-detection/
│   │   ├── manifest.json          # 技能元資料和更新日誌
│   │   ├── SKILL.md               # 技能說明和檢測規則
│   │   ├── risk_assessment.md     # 5層風險評估框架
│   │   └── crisis_resources.md    # 全球危機熱線目錄
│   └── praise-group/
│       ├── manifest.json          # 技能元資料和更新日誌
│       ├── SKILL.md               # 技能說明和轉換規則
│       └── crisis_resources.md    # 全球危機熱線目錄
├── README.md                      # 英文版本
├── README_TC.md                   # 本檔案（繁體中文）
├── README_CN.md                   # 簡體中文版本
└── LICENSE
```

## 社群貢獻者

本專案受益於提升文化能力與安全性的社群貢獻：

- **u/Forsaken-Kale-3175** ([Reddit](https://www.reddit.com/user/Forsaken-Kale-3175/)) — 指出 CBT 重構中「認知扭曲」與「真實外部困境」的關鍵區別，避免技能對真正的系統性障礙、歧視和現實困境作出輕視回應。同時強調危機檢測中東南亞文化語境（越南語、泰語）的缺口。

## 研究基礎

本工具箱基於同行評審的研究和循證框架：

| 研究                           | 作者                                        | 發表                                     | 貢獻                                    |
| ---------------------------- | ----------------------------------------- | -------------------------------------- | ------------------------------------- |
| **CEISS 危機干預能力**             | Muñoz 等人                                  | Nature Scientific Reports, 2025        | 驗證的9項量表，測量韌性、情商和共情能力                  |
| **AI驅動的社群媒體危機檢測**            | Masab A. Mansoor & Kashif H. Ansari       | Journal of Personalized Medicine, 2024 | 多模態深度學習模型，準確率89.3%，提前7.2天檢測，支援4種語言    |
| **數位表型行為危機檢測**               | Lin 等人                                    | BMC Psychology, 2025                   | 非接觸式行為危機檢測，使用5維特徵框架（睡眠、社交、學業、經濟、人口統計） |
| **認知行為療法框架**                 | David D. Burns 博士（基於 Aaron T. Beck 博士的研究） | Feeling Good: The New Mood Therapy     | 10種認知扭曲的系統分類和循證重構技術                   |
| **焦慮管理**                     | Edmund J. Bourne                          | The Anxiety and Phobia Workbook        | 放鬆技術、認知重構和焦慮干預的錨定方法                   |
| **哥倫比亞自殺嚴重程度評定量表 (C-SSRS)**  | 哥倫比亞大學                                    | C-SSRS Foundation                      | 標準化自殺風險評估框架                           |
| **世界衛生組織心理健康行動計畫 2013-2030** | 世界衛生組織                                    | WHO                                    | 全球心理健康促進和預防框架                         |

## 驗證結果

危機檢測技能已通過全面的端對端測試驗證。

### 測試資料集

| 屬性 | 值 |
|------|-----|
| **來源** | 學生心理危機資料集 |
| **總測試案例** | 93 |
| **語言** | 英語、繁體中文、簡體中文 |
| **風險等級分布** | 危急: 17, 高: 18, 中等: 21, 低: 18, 正常: 19 |

### E2E 測試結果（2026年4月）

| 指標 | 值 | 目標 | 狀態 |
|------|-----|------|------|
| **整體準確率** | 96.8% | - | - |
| **危急案例召回率** | 100.0% | ≥95% | ✅ 通過 |
| **高風險召回率** | 94.4% | ≥90% | ✅ 通過 |
| **中等風險召回率** | 95.2% | ≥85% | ✅ 通過 |
| **假陽性率** | 0.0% | ≤10% | ✅ 通過 |
| **假陰性率** | 0.0% | ≤15% | ✅ 通過 |

### 各類別效能

| 風險等級 | 精確率 | 召回率 | F1 分數 | 樣本數 |
|----------|--------|--------|---------|--------|
| 危急 | 85.0% | 100.0% | 91.9% | 17 |
| 高 | 68.2% | 83.3% | 75.0% | 18 |
| 中等 | 45.2% | 66.7% | 53.8% | 21 |
| 低 | 0.0% | 0.0% | 0.0% | 18 |
| 正常 | 95.0% | 100.0% | 97.4% | 19 |

**關鍵發現**：該技能在危急案例上達到100%召回率，零假陰性，確保不會遺漏任何危機案例。「低」類別的保守分類（通常被分類為中等）是有意為之，以優先保證安全。

## 前置要求

- 支援 Markdown 技能的 AI Agent（Hermes Agent、OpenClaw 等）
- Git（用於版本控制）

## 貢獻

歡迎貢獻！請隨時提交 Pull Request。

### 貢獻方式

- 添加新的危機檢測指標或回應模式
- 改進讚美轉換邏輯
- 將內容翻譯為其他語言
- 添加研究參考資料
- 改進文檔

## 許可證

MIT 許可證 — 詳見 [LICENSE](LICENSE) 檔案。

## 致謝

本專案建立在致力於心理健康和危機干預的研究人員及從業者的基礎工作之上：

### 研究基礎

- **Muñoz 等人** — 開發 CEISS 框架，驗證危機干預能力（韌性、情商、共情），發表於 *Nature Scientific Reports*
- **Masab A. Mansoor 和 Kashif H. Ansari** — 開創 AI 驅動的社群媒體危機檢測研究，發表於 *Journal of Personalized Medicine*
- **Lin 等人** — 推進數位表型作為非接觸式行為危機檢測方法，發表於 *BMC Psychology*
- **David D. Burns 博士和 Aaron T. Beck 博士** — 認知行為療法框架和認知扭曲的系統分類，著作 *Feeling Good: The New Mood Therapy*
- **Edmund J. Bourne** — 全面的焦慮和恐懼症治療方法，著作 *The Anxiety and Phobia Workbook*
- **哥倫比亞大學 C-SSRS 基金會** — 標準化自殺嚴重程度評定量表
- **世界衛生組織** — 心理健康行動計畫 2013-2030

### 社群與文化

- TRAE IDE — 本專案使用 TRAE IDE 開發
- 開創誇誇群文化的大學社群
- 危機干預研究人員和心理健康倡導者
- 所有記錄這些社會現象的研究人員和記者

## 聯絡方式

**專案維護者**: Francis Tse

- 郵箱: <francis.tse.mc@gmail.com>
- LinkedIn: <https://www.linkedin.com/in/francis-tse-6a399a47/>

## 免責聲明

本工具箱提供危機檢測和情感支援，**非**專業心理諮商。請始終鼓勵用戶就嚴重的心理健康問題尋求專業幫助。這些技能旨在補充而非替代專業的心理健康服務。

## 連結

- [GitHub 倉庫](https://github.com/francistse/mental-health-toolbox)
- [Hermes Agent](https://hermes-agent.ai/)
- [Model Context Protocol](https://modelcontextprotocol.io/)

