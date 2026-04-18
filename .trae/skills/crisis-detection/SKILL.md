---
name: crisis-detection
description: "Detect mental health crisis indicators using 5-tier framework. Invoke when user expresses suicidal ideation, self-harm, hopelessness, or uses /crisis, /assess, /check commands."
---

# Mental Health Crisis Detection

Proactively detect mental health crisis indicators, assess risk levels using a multi-tier evidence-based framework, and provide graduated intervention responses.

## When to Use

- User expresses suicidal ideation, self-harm, or hopelessness
- User says /crisis, /assess, /check
- Conversation reveals linguistic patterns of distress
- Behavioral indicators emerge (sleep disruption, social withdrawal)

## Risk Levels

| Score | Level | Response |
|-------|-------|----------|
| 0 | Normal | Standard interaction |
| 1 | Low | Supportive awareness |
| 2-3 | Moderate | Enhanced attention + coping strategies |
| 4-5 | High | Crisis support + resource referral |
| 6+ | Critical | Immediate intervention + safety check |

## Crisis Hotlines

| Region | Hotline | Notes |
|--------|---------|-------|
| US/Canada | 988 | Suicide & Crisis Lifeline, 24/7 |
| Hong Kong | 18111 | Government Mental Health Hotline, 24/7 |
| Taiwan | 1995 | Suicide Prevention Center, 24/7 |
| UK | 116 123 | Samaritans, 24/7 |
| Australia | 13 11 14 | Lifeline, 24/7 |
| Japan | 0570-064-556 | 24/7 |
| South Korea | 1393 | Suicide Prevention Hotline, 24/7 |

## Critical Indicators

**Direct Self-Harm Language:**
- "don't want to live" / "suicide" / "kill myself"
- "end it all" / "end my life"
- "不想活了" / "自殺" / "死にたい"

**Critical Response:**
1. Validate their courage in sharing immediately
2. Express genuine concern without being clinical
3. Provide crisis resources prominently
4. Ask directly: "Are you safe right now?"

## High-Risk Indicators

- "no point" / "hopeless" / "worthless"
- "can't go on" / "give up" / "tired of living"
- "nobody cares" / "alone" / "burden to everyone"

## Moderate-Risk Indicators

- Persistent self-deprecation
- Academic/work despair
- Social withdrawal
- Sleep/appetite disruption

## Pitfalls

### False Positive Sources
- Sarcasm/Irony may appear distressing literally
- Discussing mental health topics does NOT equal personal crisis
- Temporary emotional reactions vs. patterns

### False Negative Sources
- Subtle/gradual onset
- Indirect expression (especially in East Asian contexts)

## Disclaimer

This skill provides crisis detection and emotional support, **not** professional counseling.
