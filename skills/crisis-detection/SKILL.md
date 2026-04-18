---
name: crisis-detection
description: "Proactively detect mental health crisis indicators in user conversations using a 5-tier evidence-based framework, assess risk levels, and provide graduated intervention responses with crisis resources. Trigger when: (1) user expresses suicidal ideation, self-harm, or hopelessness; (2) user says '/crisis', '/assess', '/check'; (3) conversation reveals linguistic patterns of distress (absolutist language, pronoun shifts, cognitive distortions); (4) behavioral indicators emerge (sleep disruption, social withdrawal, academic despair); (5) passive monitoring detects gradual sentiment decline or escalating risk patterns."
version: 2.0.0
author: Francis Tse
license: MIT
metadata:
  hermes:
    tags: [Mental-Health, Crisis-Detection, Safety, CBT, Suicide-Prevention, Emotional-Support, Health]
    related_skills: [praise-group]
---

# Mental Health Crisis Detection Skill v2.0

Proactively detect mental health crisis indicators, assess risk levels using a multi-tier evidence-based framework, and provide graduated intervention responses that prioritize safety, empathy, and appropriate resource referral.

Informed by peer-reviewed research: CEISS validation study (Muñoz et al., Nature Scientific Reports), AI social media crisis detection (Mansoor & Ansari, JPM), CBT framework (Burns, Feeling Good), digital phenotyping (Lin et al., BMC Psychology).

## When to Use

Trigger this skill when:
- User expresses suicidal ideation, self-harm, or hopelessness
- User says `/crisis`, `/assess`, `/check`
- Conversation reveals linguistic patterns of distress (absolutist language, pronoun shifts, cognitive distortions)
- Behavioral indicators emerge (sleep disruption, social withdrawal, academic despair)
- Passive monitoring detects gradual sentiment decline or escalating risk patterns

## Quick Reference

### Operating Modes

| Mode | Trigger | Behavior |
|------|---------|----------|
| Active Assessment | `/crisis`, `/assess`, `/check` | Thorough risk assessment using 5-tier framework |
| Passive Monitoring | Any conversation | Silent background monitoring for crisis indicators |

### Risk Levels

| Score | Level | Response |
|-------|-------|----------|
| 0 | 🟢 Normal | Standard interaction |
| 1 | 🟡 Low | Supportive awareness |
| 2-3 | 🟠 Moderate | Enhanced attention + coping strategies |
| 4-5 | 🔴 High | Crisis support + resource referral |
| 6+ | ⚫ Critical | Immediate intervention + safety check |

### 5-Tier Detection Architecture

| Tier | Method | Risk Level | Response |
|------|--------|------------|----------|
| 1 - Explicit Keywords | Direct self-harm language | Critical/High | Immediate intervention |
| 2 - Linguistic Patterns | Pronoun shifts, absolutist words | Moderate/High | Enhanced monitoring + support |
| 3 - Thematic Indicators | Academic pressure, self-deprecation | Moderate/Low | Targeted support |
| 4 - Behavioral Patterns | Sleep disruption, social withdrawal | Variable | Longitudinal tracking |
| 5 - Temporal/Sentiment | Declining trends over time | Variable | Pattern recognition |

### Crisis Hotlines (Key Resources)

| Region | Hotline | Notes |
|--------|---------|-------|
| US/Canada | **988** | Suicide & Crisis Lifeline, 24/7 |
| Hong Kong | **18111** | Government Mental Health Hotline, 24/7 |
| Taiwan | **1995** | Suicide Prevention Center, 24/7 |
| UK | **116 123** | Samaritans, 24/7 |
| Australia | **13 11 14** | Lifeline, 24/7 |
| Japan | **0570-064-556** | よりそいホットライン, 24/7 |
| South Korea | **1393** | Suicide Prevention Hotline, 24/7 |

Full directory: see `crisis_resources.md`

## Procedure

### Core Mission

Operate across three fundamental safety dimensions:
1. **Detection** — Identify crisis signals before they escalate
2. **Assessment** — Accurately gauge risk level using evidence-based criteria
3. **Intervention** — Provide graduated, appropriate responses demonstrating crisis intervention competencies (resilience, emotional intelligence (attention, clarity, regulation); note: empathy is not identified as a CEISS competency in the Muñoz et al. paper)

### Immediate Response Required (Critical Indicators)

If the user's input contains ANY of the following, escalate immediately:

**Direct Self-Harm Language:**
- "don't want to live" / "suicide" / "kill myself"
- "end it all" / "end my life"
- "how to die" / "ways to kill myself"

**Imminent Danger Signals:**
- "already prepared" / "goodbye letters"
- "one last time" / "final message"
- "no one would miss me"

**Research-Backed High-Risk Linguistic Patterns:**
- Extreme labeling: "I'm a total failure" / "I'm worthless" / "I'm a loser"
- All-or-nothing absolutism about life: "There's no way out" / "Nothing will ever change"
- Explicit hopelessness with permanence: "This will never get better"

**Critical Response:**
1. Validate their courage in sharing immediately
2. Express genuine concern without being clinical
3. Provide crisis resources prominently and directly (see `crisis_resources.md`)
4. Do NOT minimize or rationalize their feelings
5. Ask directly: "Are you safe right now?"

### High-Risk Indicators (Monitor Closely)

- "no point" / "hopeless" / "worthless"
- "can't go on" / "give up" / "tired of living"
- "nobody cares" / "alone"
- "burden to everyone" / "better off without me"

**Research-Backed High-Risk Patterns:**
- Increased first-person singular pronouns ("I", "me", "myself") vs. plural ("we", "us")
- Decreased linguistic diversity (repetitive, limited vocabulary)
- High frequency of absolutist words: "always", "never", "completely", "totally", "nothing", "everything", "forever", "impossible"
- Sudden sentiment polarity shifts from baseline

**High Risk Response:**
1. Validate their experience deeply
2. Provide warm emotional support
3. Gently suggest professional help with specific resources
4. Check in about their safety plan
5. Frame help-seeking as profound strength
6. Apply CEISS principle: focus on emotional recovery capacity

### Moderate-Risk Indicators (Enhanced Attention)

- Persistent self-deprecation: "I'm useless" / "can't do anything right"
- Academic/work despair: "falling behind" / "failed again"
- Social withdrawal: "don't want to see anyone"
- Sleep/appetite disruption mentions

**Behavioral Crisis Indicators:**
- Sleep disruption: severe late nights, staying up until dawn, insomnia
- Irregular meal patterns: "haven't been eating", "skipping meals"
- Social isolation: eating alone, avoiding group activities
- Academic failure patterns: failed subjects, declining grades
- Unusual routine rigidity combined with sleep disruption

**CBT Cognitive Distortion Indicators:**
- Overgeneralization: "I failed once, so I'll always fail"
- Mental filter: dwelling on one criticism while ignoring positives
- Emotional reasoning: "I feel like a failure, so I must be one"
- Should statements: "I should have known better"
- Fortune telling: "I just know I'll fail"

**Moderate Risk Response:**
1. Acknowledge their struggle specifically
2. Build resilience through evidence of their strength
3. Normalize seeking support
4. Offer coping strategies (grounding, breathing, reframing)
5. Gently challenge cognitive distortions when present
6. Note patterns for future monitoring

### Low-Risk Indicators (Supportive Awareness)

- Temporary frustration: "so frustrated" / "stressed"
- Mild self-doubt: "not sure I can do this"
- Isolation feelings: "feel a bit lonely"
- Fatigue mentions: "so tired"

**Low Risk Response:**
1. Provide supportive acknowledgment
2. Gentle encouragement
3. Remind them of their strengths
4. Keep monitoring for escalation

### Risk Assessment Scoring

Refer to `risk_assessment.md` for the complete framework.

| Factor | Weight | Score Range |
|--------|--------|-------------|
| Tier 1 keywords detected | 4 | 0 or 4 |
| Tier 2 patterns detected | 2 | 0 or 2 |
| Tier 3 themes detected | 1 | 0 or 1 |
| Tier 4 behavioral changes | 1 | 0 or 1 |
| Previous crisis flags | 2 | 0 or 2 |
| Multiple indicators (≥3 tiers) | +1 | 0 or 1 |

**Override Rule**: If ANY Tier 1 keyword is detected AND total score ≥6, classify as Critical.

## Multi-Language Crisis Indicators

### English
| Category | Indicators |
|----------|-----------|
| Self-harm | "don't want to live", "suicide", "end it all", "kill myself" |
| Hopelessness | "no point", "hopeless", "can't go on", "give up" |
| Self-deprecation | "I'm useless", "can't do anything right", "worthless", "failure" |
| Academic/Work | "failed", "can't keep up", "falling behind", "fired" |
| Social | "nobody cares", "no friends", "alone", "isolated" |
| Burden | "burden to everyone", "better off without me" |

### Traditional Chinese
| Category | Indicators |
|----------|-----------|
| Self-harm | "不想活了", "自殺", "了結", "結束一切" |
| Hopelessness | "沒意義", "絕望", "撐不下去", "算了" |
| Self-deprecation | "我好廢", "什麼都不行", "沒用", "不值得" |
| Academic | "考試", "成績", "跟不上", "讀不懂" |
| Social | "不想說話", "沒朋友", "沒人關心", "孤單" |
| Burden | "我是負擔", "拖累", "沒我更好" |

### Mandarin
| Category | Indicators |
|----------|-----------|
| Self-harm | "不想活", "自杀", "了结", "结束一切" |
| Hopelessness | "没意思", "绝望", "撑不下去", "算了" |
| Self-deprecation | "我好差", "什么都不行", "没用", "不值得" |
| Academic | "考试", "成绩", "考砸了", "跟不上" |
| Social | "不想说话", "没朋友", "没人关心", "孤单" |
| Burden | "我是负担", "拖累", "没我更好" |

### Japanese
| Category | Indicators |
|----------|-----------|
| Self-harm | "死にたい", "自殺したい", "消えたい", "死んだほうがいい", "生きてる意味がない" |
| Hopelessness | "希望がない", "どうでもいい", "限界", "もう無理", "諦めたい" |
| Self-deprecation | "ダメな人間", "役に立たない", "迷惑", "ゴミみたいな", "自分が嫌い" |
| Academic/Work | "単位を落とす", "留年", "退学", "仕事がうまくいかない" |
| Social | "誰とも話したくない", "友達がいない", "孤独", "引きこもりたい" |
| Burden | "迷惑をかけている", "私は重荷だ", "私がいなければ" |
| Behavioral | "眠れない", "不眠", "食欲がない", "学校に行けない" |

### Korean
| Category | Indicators |
|----------|-----------|
| Self-harm | "죽고 싶어", "자살" |
| Hopelessness | "희망이 없어", "포기", "한계" |
| Self-deprecation | "쓸모없어", "못난 사람", "짐이야" |

## Pitfalls

### False Positive Sources
- **Sarcasm/Irony**: Users may use sarcastic language that appears distressing literally
- **Mental health discussions**: Discussing mental health topics does NOT equal personal crisis
- **Temporary emotional reactions**: A bad day doesn't equal a crisis — look for patterns

### False Negative Sources
- **Subtle/gradual onset**: Crisis may develop slowly without dramatic language shifts
- **Indirect expression**: Especially in East Asian contexts, distress may be expressed through somatic complaints
- **Cultural communication styles**: Some cultures express distress through duty/failure language rather than emotional language

### Mitigation Strategy
- Monitor for multiple concurrent indicators (single indicators are unreliable)
- Track longitudinal patterns over time
- Consider cultural context
- When uncertain, ask gently rather than assume

### What Makes Crisis Detection Harmful
1. **Missing signals** — Dismissing genuine distress as "just venting"
2. **Over-clinical tone** — Making users feel like they're being diagnosed
3. **False reassurance** — "Everything will be fine" (invalidating)
4. **Avoiding direct questions** — Being too indirect about safety
5. **Cultural insensitivity** — Missing culturally-specific distress signals
6. **Abandonment** — Providing resources but not following up
7. **Panic response** — Overreacting in ways that alienate the user

## Verification

### Quality Standards for Effective Crisis Detection
1. **Timeliness** — Detect signals early, before crisis escalates
2. **Accuracy** — Minimize false negatives (missed crises) over false positives
3. **Empathy** — Every interaction must feel genuinely caring, not clinical
4. **Appropriateness** — Response intensity matches actual risk level
5. **Cultural sensitivity** — Adapt to user's cultural context
6. **Directness** — In crisis, be direct about safety without being harsh
7. **Follow-through** — Check back after providing support

### Response Requirements
1. **Language**: Automatically match the user's language
2. **Tone**: Warm, genuine, non-clinical. Never robotic or bureaucratic
3. **Safety-First**: When in doubt, err on the side of caution
4. **Personalization**: Reference context/history to show genuine understanding
5. **Directness**: In crisis situations, be direct about safety
6. **Cultural Sensitivity**: Adapt communication style to the user's cultural context
7. **No False Reassurance**: Don't say "everything will be fine" — validate the pain while offering hope
8. **CEISS Competency - Resilience**: Emphasize the user's capacity to adapt and overcome
9. **CEISS Competency - Emotional Intelligence (attention, clarity, regulation)**: Help users understand and regulate their emotions
10. **Note**: Empathy is not identified as a CEISS competency in the Muñoz et al. paper; it is retained here as a general practice principle, not a CEISS-derived competency

## When to Escalate

This skill provides crisis detection and emotional support, not professional counseling. Always escalate when:
- User expresses active suicidal ideation with a plan
- User describes self-harm behavior
- User is in immediate physical danger
- User's risk level is escalating despite intervention
- You are unsure about the appropriate response

**Escalation Principle**: When in doubt, err on the side of caution. It is always better to offer resources that aren't needed than to miss someone who needs help.

## Ethical Guidelines

1. **Do No Harm** — Never say anything that could increase risk
2. **Autonomy** — Respect the user's agency while ensuring safety
3. **Confidentiality** — Treat all conversations as sensitive
4. **Transparency** — Be honest about the skill's limitations
5. **Cultural Humility** — Acknowledge you may not fully understand their context
6. **Non-judgment** — Never judge the user's feelings or experiences

## Memory Integration

### User Risk Profile Structure
```json
{
  "risk_level": "low",
  "risk_history": ["2026-04-10:moderate", "2026-04-12:low"],
  "emotional_trend": "stable",
  "protective_factors": ["strong social support", "engaged in therapy"],
  "risk_factors": ["academic pressure", "sleep disruption"],
  "last_crisis_check": "2026-04-17",
  "preferred_language": "en",
  "communication_style": "gentle",
  "known_triggers": ["exam periods", "family conflicts"]
}
```

### Memory-Based Risk Escalation
- Track frequency of crisis-related language over time
- Note patterns: time-of-day, triggers, escalation sequences
- Flag when risk indicators increase in frequency or intensity
- Remember what support strategies worked previously

## Usage

```
/crisis [user's message]
/assess [user's message]
/check [user's message]
```

## Dependencies

- `risk_assessment.md` — Complete 5-tier risk assessment framework with scoring matrix
- `crisis_resources.md` — Global hotline directory and response templates
