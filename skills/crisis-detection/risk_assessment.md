# Risk Assessment Framework - Research-Enhanced Edition (v2.0)

*Version 2.0 | Peer-reviewed research: CEISS (Muñoz et al., Nature Sci Reports), AI Social Media Detection (Mansoor & Ansari, PMC11433454), CBT (Burns, Feeling Good) | Updated with digital phenotyping findings*

## Overview

This framework provides a structured, evidence-based approach to assessing mental health crisis risk in conversational AI interactions. It integrates validated findings from:
- CEISS psychometric validation study (9-item scale, McDonald's ω = 0.90)
- AI social media crisis detection study (89.3% accuracy, 7.2-day lead time)
- Cognitive Behavioral Therapy cognitive distortion framework
- Anxiety management research (Bourne, Anxiety and Phobia Workbook)
- Digital phenotyping research (Lin et al., 2025): Enhanced behavioral indicators based on behavioral data from 4,508 college students.

## 5-Tier Detection Architecture

### Tier 1: Explicit Keywords (Immediate Flagging)

**Purpose**: Detect direct expressions of crisis that require immediate intervention.

**Detection Method**: Keyword matching against curated crisis vocabulary.

| Category | English | Traditional Chinese | Mandarin | Japanese |
|----------|---------|-------------------|----------|----------|
| **Self-harm intent** | "suicide", "kill myself", "end my life" | "自殺", "不想活了", "了結" | "自杀", "不想活", "了结" | "死にたい", "自殺したい", "消えたい", "死んだほうがいい" |
| **Death references** | "end it all", "no reason to live" | "結束一切", "活著沒意義" | "结束一切", "活着没意义" | "生きてる意味がない", "生きていても仕方ない", "終わりにしたい" |
| **Method mentions** | "how to die", "ways to end it" | "死亡方式", "怎麼死" | "死亡方式", "怎么死" | "死に方", "どうやって死ぬ" |
| **Farewell signals** | "goodbye forever", "final message" | "最後的告別", "遺書" | "最后的告别", "遗书" | "さようなら", "最後のメッセージ", "遺書" |

**Risk Level**: Critical - Immediate intervention required

---

### Tier 2: Linguistic Patterns (Monitoring)

**Purpose**: Detect subtle linguistic shifts that correlate with deteriorating mental health.

#### 2.1 Pronoun Shift Analysis

| Pattern | Indicator | Significance |
|---------|-----------|--------------|
| Increased first-person singular | "I", "me", "my" vs. "we", "us", "our" | Social disconnection |
| Decreased first-person plural | Reduced "we", "us" references | Withdrawal from social identity |
| Second-person references to self | "You know how it is when..." | Dissociation |

#### 2.2 Absolutist Language

Research shows that absolutist language is strongly correlated with mental health crises. The AI social media study found that high frequency of these words was a key predictive marker:

| English | Traditional Chinese | Mandarin | Japanese | Significance |
|---------|-------------------|----------|----------|--------------|
| "always", "never" | "總是", "從來不" | "总是", "从来不" | "いつも", "決して", "絶対" | Cognitive distortion (overgeneralization) |
| "completely", "totally" | "完全", "徹底" | "完全", "彻底" | "完全に", "全く", "本当に" | All-or-nothing thinking |
| "nothing", "everything" | "什麼都", "一切" | "什么都", "一切" | "何も", "全て", "何もかも" | Overgeneralization |
| "forever", "impossible" | "永遠", "不可能" | "永远", "不可能" | "永遠に", "無理", "できない" | Perceived permanence |

#### 2.3 Decreased Linguistic Diversity

A validated marker from the AI social media study:

| Indicator | Detection | Risk Implication |
|-----------|-----------|-----------------|
| Repetitive vocabulary | Same words/phrases used repeatedly | Cognitive narrowing — user stuck in thought loop |
| Shorter responses | Decreased response length over time | Emotional flattening or withdrawal |
| Loss of metaphor/creativity | Previously creative language becomes flat | Loss of cognitive flexibility |

#### 2.4 Emotional Vocabulary Shifts

| Direction | Indicators | Risk Implication |
|-----------|-----------|-----------------|
| Increased negative emotion words | "sad", "angry", "scared" | Emotional distress |
| Decreased positive emotion words | Fewer "happy", "hope", "excited" | Anhedonia |
| Increased death/illness words | "death", "pain", "suffering" | Morbid preoccupation |
| Emotional flattening | Short, unemotional responses | Emotional numbness |

**Risk Level**: High - Enhanced monitoring + proactive support

---

### Tier 3: Thematic Indicators (Contextual Assessment)

**Purpose**: Identify thematic content that signals specific risk factors.

#### 3.1 Academic/Work Pressure

| English | Traditional Chinese | Mandarin | Japanese |
|---------|-------------------|----------|----------|
| "failed", "can't keep up", "falling behind" | "考砸了", "跟不上", "讀不懂" | "考砸了", "跟不上" | "単位を落とす", "留年", "成績が落ちた", "課題が出せない" |
| "fired", "laid off", "useless at work" | "被辭退", "工作做不好" | "被辞退", "工作做不好" | "クビになりそう", "仕事がうまくいかない" |
| "disappointed everyone", "let them down" | "讓人失望", "辜負期望" | "让人失望", "辜负期望" | "みんなに失望させた", "期待に応えられない" |

#### 3.2 Self-Deprecation & Worthlessness

| English | Traditional Chinese | Mandarin | Japanese |
|---------|-------------------|----------|----------|
| "I'm stupid", "can't do anything right" | "我好廢", "什麼都不行" | "我好差", "什么都不行" | "ダメな人間", "自分が嫌い", "情けない" |
| "worthless", "failure", "waste of space" | "沒用", "不值得", "浪費" | "没用", "不值得" | "役に立たない", "生きている価値がない", "ゴミみたいな" |

#### 3.3 Social Withdrawal & Isolation

| English | Traditional Chinese | Mandarin | Japanese |
|---------|-------------------|----------|----------|
| "don't want to see anyone" | "不想見人", "不想出門" | "不想见人", "不想出门" | "誰とも話したくない", "人に会いたくない", "引きこもりたい" |
| "nobody understands me" | "沒人懂我", "沒人關心" | "没人懂我", "没人关心" | "誰も理解してくれない", "孤独", "友達がいない" |

#### 3.4 Burden Perception

| English | Traditional Chinese | Mandarin | Japanese |
|---------|-------------------|----------|----------|
| "burden to everyone" | "我是負擔", "拖累大家" | "我是负担", "拖累大家" | "迷惑をかけている", "私は重荷だ" |
| "better off without me" | "沒我更好", "少了我沒差" | "没我更好" | "私がいなければ", "みんなのために消えたほうがいい", "家族に申し訳ない" |

**Risk Level**: Moderate - Targeted support + active listening

---

### Tier 4: Behavioral Patterns (Longitudinal Tracking)

**Purpose**: Detect behavioral changes over time that indicate deteriorating mental health.

**Updated with digital phenotyping findings** — behavioral features contribute the highest importance to crisis classification (Lin et al., 2025). Sleep disruption alone has an importance score of 14.01, making it the single strongest predictor.

#### 4.1 Engagement Pattern Changes

| Pattern | Indicator | Risk Implication |
|---------|-----------|-----------------|
| Decreased interaction frequency | Fewer messages, longer gaps | Withdrawal |
| Timing shifts | Late-night only, unusual hours | Sleep disruption (importance: 14.01) |
| Response length changes | Shorter responses over time | Emotional flattening |
| Topic avoidance | Steering away from previously enjoyed topics | Anhedonia |

#### 4.2 Sleep and Health Indicators (Highest Behavioral Importance)

| Behavioral Marker | Indicator | Risk Correlation |
|-------------------|-----------|------------------|
| Severe late-night activity | Mentions of staying up until dawn, 2-6 AM activity | r = 0.377, p < 0.001 |
| Irregular meal patterns | Skipping meals, irregular eating times | Top 5 importance features |
| Skipping breakfast regularly | "don't eat breakfast", "no morning routine" | Crisis indicator |
| Days away from campus/school | Mentions of not going to school/work | Importance: 7.09 |
| Unusual routine rigidity | Overly strict schedules + sleep disruption | Paradoxical crisis signal |
| 日本語睡眠指標 | "眠れない", "不眠", "朝まで寝られない", "食欲がない", "学校に行けない", "部屋から出られない" | Japanese cultural markers |

**Key Finding**: Students in psychological crisis showed unusually regular life patterns combined with severe late nights — they barely ate breakfast, had highly regular daily mealtimes, but stayed up very late. This suggests that **rigid routines with sleep disruption** can be as significant as chaotic behavior.

#### 4.3 Social Withdrawal Behavioral Indicators

| Behavioral Marker | Indicator | Risk Correlation |
|-------------------|-----------|------------------|
| Decreased meal co-occurrence | Eating alone, avoiding group meals | r = -0.403 (strongest protective when present) |
| Social isolation mentions | "eating alone", "no one to hang out with" | Strong negative correlation |
| Roommate/classmate withdrawal | Avoiding social interactions | Significant protective factor loss |

#### 4.4 Academic/Work Performance Indicators

| Behavioral Marker | Indicator | Risk Correlation |
|-------------------|-----------|------------------|
| Failed subjects/exams | "failed my test", "flunked", "academic probation" | Significant positive correlation |
| GPA decline mentions | "my grades are dropping" | r = -0.227 |
| Academic pressure themes | Study stress, exam anxiety | Dominant theme in East Asian contexts |

#### 4.5 Emotional Trajectory

| Trajectory | Pattern | Risk Implication |
|-----------|---------|-----------------|
| Declining | Negative sentiment increasing | Deteriorating mental health |
| Volatile | Rapid swings | Emotional instability |
| Flat | Consistently neutral | Emotional numbness |
| Improving | Positive trend | Recovery (continue monitoring) |

**Risk Level**: Variable - Longitudinal tracking + proactive check-ins

---

### Tier 5: Temporal/Sentiment Analysis (Pattern Recognition)

**Purpose**: Detect trends over time that are more predictive than single data points.

**Key Research Finding**: The AI social media study found that gradual sentiment decline over time was more predictive of crisis than single assessment points. Sudden sentiment polarity shifts specifically preceded manic or mixed episodes.

| Trajectory | Pattern | Risk Implication |
|-----------|---------|-----------------|
| Gradual decline | Slowly increasing negative sentiment over weeks/months | Most predictive of eventual crisis |
| Sudden polarity shift | Dramatic change from negative to positive (or vice versa) | May indicate manic/mixed episode |
| Volatile | Rapid swings between positive and negative | Emotional instability |
| Flat | Consistently neutral, unemotional responses | Emotional numbness |
| Improving | Positive trend | Recovery (continue monitoring) |

**Detection Method**: Compare sentiment across interactions over time. Track emotional trajectory across at least 3 data points for reliability.

**Risk Level**: Variable - Pattern recognition + proactive check-ins

---

## Risk Level Classification

### Scoring Matrix

| Factor | Weight | Score Range | Notes |
|--------|--------|-------------|-------|
| Tier 1 keywords detected | 4 | 0 or 4 | Direct self-harm language — highest weight |
| Tier 2 patterns detected | 2 | 0 or 2 | Absolutist language, pronoun shifts |
| Tier 3 themes detected | 1 | 0 or 1 | Self-deprecation, academic despair |
| Tier 4 behavioral changes | 1 | 0 or 1 | Sleep disruption, social withdrawal |
| Previous crisis flags | 2 | 0 or 2 | History matters — longitudinal context |
| Multiple indicators combined | +1 | 0 or 1 | **Only applies if ≥3 different tiers are active** |

### Risk Level Thresholds

| Total Score | Risk Level | Color Code | Required Response |
|-------------|-----------|------------|-------------------|
| 0 | Normal | Green | Standard interaction |
| 1 | Low | Yellow | Supportive awareness |
| 2-3 | Moderate | Orange | Enhanced attention + targeted support |
| 4-5 | High | Red | Crisis support + resource referral |
| 6-7 | High+ | Red+ | Enhanced crisis support + safety inquiry |
| 8+ | Critical | Black | Immediate intervention + safety check |

**Safety Note**: The Critical threshold (8+) is intentionally set high to require Tier 1 presence plus multiple other indicators, OR multiple Tier 1 indicators with history. Cases scoring 6-7 without Tier 1 keywords are classified as High+ rather than Critical to prevent over-escalation from combined Tier 2/3/4 indicators alone. This preserves safety (still triggers crisis support) while avoiding unnecessary critical-level responses.

**Override Rule**: If ANY Tier 1 keyword is detected AND the total score is ≥6, classify as Critical regardless of the numeric threshold. The presence of direct self-harm language combined with any additional indicators warrants immediate intervention.

---

## Graduated Response Protocol

### Normal (Green)
- Standard conversational interaction
- No special intervention needed
- Continue passive monitoring

### Low (Yellow)
- Supportive acknowledgment of feelings
- Gentle encouragement
- Remind user of their strengths
- Log interaction for trend tracking

### Moderate (Orange)
- Active empathy and validation
- Resilience-building responses
- Normalize seeking support
- Offer coping strategies
- Enhanced monitoring frequency

### High (Red)
- Direct emotional support
- Gentle but explicit resource suggestion
- Safety inquiry (without being clinical)
- Frame help-seeking as strength
- Check in about their support network
- Log as high-priority for follow-up

### Critical (Black)
- Immediate safety check: "Are you safe right now?"
- Direct crisis resource provision
- Do not leave the conversation unresolved
- Validate their courage in sharing
- Express genuine concern
- Ask about safety plan
- If possible, encourage connection with a trusted person
- Mandatory follow-up check

---

## Cultural Considerations

### East Asian Context (HK, TW, CN, JP, KR)
- Mental health stigma may cause indirect expression of distress
- Watch for somatic complaints as proxy for emotional distress
- Academic/family pressure is a dominant theme
- "Saving face" may suppress direct crisis language
- Shame-based distress requires extra sensitivity

### Western Context (US, UK, CA, AU)
- More direct expression of emotional distress
- Greater familiarity with mental health terminology
- Therapy culture may normalize help-seeking
- Watch for "therapy-speak" that masks genuine crisis

### Cross-Cultural Principles
- Never assume cultural norms - let the user lead
- Adapt resource suggestions to local availability
- Respect cultural communication styles
- When uncertain, ask gently rather than assume

---

## Integration with Crisis Resources

When risk assessment indicates High or Critical levels, reference `crisis_resources.md` for:
- Region-specific crisis hotlines
- Culturally appropriate support services
- Multi-language resource matching

**Matching Logic**:
1. Detect user's likely region from language and content
2. Select appropriate resources from crisis_resources.md
3. Present resources naturally within the response
4. Frame resource use as a sign of strength

---

## Limitations & Disclaimers

1. This assessment framework is a **screening tool**, not a diagnostic instrument
2. Risk levels are **probabilistic indicators**, not clinical diagnoses
3. The framework may produce **false positives** and **false negatives**
4. Cultural and linguistic nuances may affect accuracy
5. Always defer to professional mental health assessment
6. When in doubt, **err on the side of caution**

---

## References

1. Muñoz, M., et al. "Development of the Crisis and Emergency Intervention Skills Scale (CEISS) and an analysis of its psychometric properties." Nature Scientific Reports, s41598-025-86992-y, 2025. (Validated 9-item scale, McDonald's ω = 0.90, correlations with resilience and emotional intelligence)
2. Mansoor, M.A., Ansari, K.H. "Early Detection of Mental Health Crises through Artificial-Intelligence-Powered Social Media Analysis: A Prospective Observational Study." PMC11433454, 2026. (89.3% accuracy, 7.2-day lead time, 996,452 posts, 4 languages, 3 platforms)
3. Burns, D.D. "Feeling Good: The New Mood Therapy." Cognitive Behavioral Therapy framework for cognitive distortion identification.
4. Bourne, E.J. "The Anxiety and Phobia Workbook." Evidence-based anxiety management techniques.
5. Hospital Authority, Hong Kong. "Service Framework for Adults with Severe Mental Illness." Care pathways and multidisciplinary team approaches.
6. WHO Mental Health Action Plan 2013-2030
7. Columbia Suicide Severity Rating Scale (C-SSRS) framework
8. Lin, J., Tian, J., Wang, T.Y., Li, D., Jiang, X. "Psychological crisis detection based on behavioral data: a new approach to non-contact measurement." BMC Psychology, 2025. s40359-025-03604-0.
