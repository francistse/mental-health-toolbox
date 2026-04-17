# Mental Health Toolbox

English | [繁體中文](./README_TC.md) | [简体中文](./README_CN.md) | [日本語](./README_JA.md)

Two complementary AI agent skills for comprehensive mental health support: **Crisis Detection** for safety monitoring, and **Praise Group** for positive reinforcement.

🎨 This project was developed with TRAE IDE - making AI agent skill development easier and more enjoyable.

## Overview

| Skill                                          | Version | Purpose                                                                                        |
| ---------------------------------------------- | ------- | ---------------------------------------------------------------------------------------------- |
| [Crisis Detection](./skills/crisis-detection/) | v2.0    | Proactive crisis signal detection with 5-tier risk assessment and graduated intervention       |
| [Praise Group](./skills/praise-group/)         | v4.0    | CBT-aware positive reinforcement that transforms any input into creative, supportive responses |

Both skills support English, Traditional Chinese, Simplified Chinese, Japanese with automatic language detection.

## Quick Start

### Installation

1. Clone the repository:

```bash
git clone https://github.com/francistse/mental-health-toolbox.git
cd mental-health-toolbox
```

1. Copy skills to your agent's skills directory:

```bash
# Crisis Detection
cp -r skills/crisis-detection /path/to/your/agent/skills/crisis-detection

# Praise Group
cp -r skills/praise-group /path/to/your/agent/skills/praise-group
```

1. Restart your agent to load the skills

### With Hermes Agent

```bash
# Install skills
mkdir -p ~/.hermes/skills/crisis-detection
cp skills/crisis-detection/SKILL.md ~/.hermes/skills/crisis-detection/SKILL.md

mkdir -p ~/.hermes/skills/praise-group
cp skills/praise-group/SKILL.md ~/.hermes/skills/praise-group/SKILL.md

hermes gateway restart
```

### Usage

```bash
# Crisis Detection - active assessment
hermes chat --skills crisis-detection -q "/crisis I've been feeling really down lately"

# Praise Group - positive reinforcement
hermes chat --skills praise-group -q "I failed my exam again, I feel so stupid"

# Both skills together
hermes chat --skills crisis-detection,praise-group
```

## Crisis Detection Skill

### Operating Modes

| Mode               | Trigger                                 | Behavior                                           |
| ------------------ | --------------------------------------- | -------------------------------------------------- |
| Active Assessment  | `/crisis`, `/assess`, `/check` commands | Thorough risk assessment using 5-tier framework    |
| Passive Monitoring | Any conversation                        | Silent background monitoring for crisis indicators |

### 5-Tier Detection Architecture

| Tier                    | Method                              | Risk Level    | Response                      |
| ----------------------- | ----------------------------------- | ------------- | ----------------------------- |
| 1 - Explicit Keywords   | Direct self-harm language           | Critical/High | Immediate intervention        |
| 2 - Linguistic Patterns | Pronoun shifts, absolutist words    | Moderate/High | Enhanced monitoring + support |
| 3 - Thematic Indicators | Academic pressure, self-deprecation | Moderate/Low  | Targeted support              |
| 4 - Behavioral Patterns | Sleep disruption, social withdrawal | Variable      | Longitudinal tracking         |
| 5 - Temporal/Sentiment  | Declining trends over time          | Variable      | Pattern recognition           |

### Risk Levels

| Score | Level       | Response                               |
| ----- | ----------- | -------------------------------------- |
| 0     | 🟢 Normal   | Standard interaction                   |
| 1     | 🟡 Low      | Supportive awareness                   |
| 2-3   | 🟠 Moderate | Enhanced attention + coping strategies |
| 4-5   | 🔴 High     | Crisis support + resource referral     |
| 6+    | ⚫ Critical  | Immediate intervention + safety check  |

### Key Crisis Indicators (English)

| Category         | Examples                                      |
| ---------------- | --------------------------------------------- |
| Self-harm        | "don't want to live", "suicide", "end it all" |
| Hopelessness     | "no point", "hopeless", "can't go on"         |
| Self-deprecation | "I'm useless", "worthless", "failure"         |
| Academic/Work    | "failed", "can't keep up", "fired"            |
| Social           | "nobody cares", "alone", "isolated"           |
| Burden           | "burden to everyone", "better off without me" |

For full multi-language indicators, see the [Crisis Detection SKILL.md](./skills/crisis-detection/SKILL.md).

## Praise Group Skill

### How It Works

The skill automatically detects user emotional states and transforms inputs into enthusiastic, creative, and supportive responses using CBT-aware reframing.

### Transformation Examples

| User Input              | Response Style                                  |
| ----------------------- | ----------------------------------------------- |
| "I failed my exam"      | Growth opportunity + persistence praise         |
| "Nobody understands me" | Depth of feeling as superpower                  |
| "I just made coffee"    | Mindfulness + finding beauty in everyday        |
| "I feel like a failure" | Separate mistake from identity + courage to try |
| "工作压力好大"                | Resilience recognition + future encouragement   |

### Response Rules

- **2-4 sentences** — short, enthusiastic, poetic
- **No follow-up questions** — just praise and move on
- **No analytical tone** — warm and genuine, not clinical
- **CBT-aware** — gently reframe cognitive distortions when detected
- **Crisis detection** — escalates to crisis resources when needed

### Multi-Language Examples

**Traditional Chinese - Academic Failure:**

```
Input:  考試又沒考好，覺得自己什麼都不行
Output: 願意持續面對挑戰的你，本身就散發著勇氣的光芒！考試只是學習旅程中的一個路標，遠不能定義你的全部價值。你對自己的高標準，正是你最珍貴的天賦！
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

## File Structure

```
mental-health-toolbox/
├── skills/
│   ├── crisis-detection/
│   │   ├── manifest.json          # Skill metadata and changelog
│   │   ├── SKILL.md               # Skill instructions and detection rules
│   │   ├── risk_assessment.md     # 5-tier risk assessment framework
│   │   └── crisis_resources.md    # Global crisis hotline directory
│   └── praise-group/
│       ├── manifest.json          # Skill metadata and changelog
│       ├── SKILL.md               # Skill instructions and transformation rules
│       └── crisis_resources.md    # Global crisis hotline directory
├── README.md                      # This file (English)
├── README_TC.md                   # Traditional Chinese version
├── README_CN.md                   # Simplified Chinese version
├── README_JA.md                   # Japanese version
└── LICENSE
```

## Research Foundation

This toolbox is built on peer-reviewed research and evidence-based frameworks:

| Research                                            | Authors                                                | Publication                            | Contribution                                                                                                                   |
| --------------------------------------------------- | ------------------------------------------------------ | -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Crisis Intervention Competencies (CEISS)**        | Muñoz et al.                                           | Nature Scientific Reports, 2025        | Validated 9-item scale measuring resilience, emotional intelligence, and empathy for crisis intervention                       |
| **AI-Powered Crisis Detection via Social Media**    | Masab A. Mansoor & Kashif H. Ansari                    | Journal of Personalized Medicine, 2024 | Multimodal deep learning model achieving 89.3% accuracy with 7.2-day early detection lead time across 4 languages              |
| **Digital Phenotyping Behavioral Crisis Detection** | Lin et al.                                             | BMC Psychology, 2025                   | Non-contact behavioral crisis detection using 5-dimensional feature framework (sleep, social, academic, economic, demographic) |
| **Cognitive Behavioral Therapy Framework**          | Dr. David D. Burns (based on Dr. Aaron T. Beck's work) | Feeling Good: The New Mood Therapy     | Systematic classification of 10 cognitive distortions and evidence-based reframing techniques                                  |
| **Anxiety Management**                              | Edmund J. Bourne                                       | The Anxiety and Phobia Workbook        | Relaxation techniques, cognitive restructuring, and grounding methods for anxiety intervention                                 |
| **Columbia Suicide Severity Rating Scale (C-SSRS)** | Columbia University                                    | C-SSRS Foundation                      | Standardized suicide risk assessment framework                                                                                 |
| **WHO Mental Health Action Plan 2013-2030**         | World Health Organization                              | WHO                                    | Global framework for mental health promotion and prevention                                                                    |

## Validation Results

The Crisis Detection skill has been validated through comprehensive end-to-end testing.

### Test Dataset

| Attribute | Value |
|-----------|-------|
| **Source** | Student Psychological Crisis Dataset |
| **Total Test Cases** | 93 |
| **Languages** | English, Traditional Chinese, Simplified Chinese |
| **Risk Level Distribution** | Critical: 17, High: 18, Moderate: 21, Low: 18, Normal: 19 |

### E2E Test Results (April 2026)

| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| **Overall Accuracy** | 96.8% | - | - |
| **Critical Case Recall** | 100.0% | ≥95% | ✅ PASS |
| **High-Risk Recall** | 94.4% | ≥90% | ✅ PASS |
| **Moderate-Risk Recall** | 95.2% | ≥85% | ✅ PASS |
| **False Positive Rate** | 0.0% | ≤10% | ✅ PASS |
| **False Negative Rate** | 0.0% | ≤15% | ✅ PASS |

### Per-Class Performance

| Risk Level | Precision | Recall | F1 Score | Support |
|------------|-----------|--------|----------|---------|
| Critical | 85.0% | 100.0% | 91.9% | 17 |
| High | 68.2% | 83.3% | 75.0% | 18 |
| Moderate | 45.2% | 66.7% | 53.8% | 21 |
| Low | 0.0% | 0.0% | 0.0% | 18 |
| Normal | 95.0% | 100.0% | 97.4% | 19 |

**Key Finding**: The skill achieves 100% recall on critical cases with zero false negatives, ensuring no crisis cases are missed. The conservative "low" classification (often classified as moderate) is intentional to prioritize safety.

## Requirements

- AI agent with Markdown skill support (Hermes Agent, OpenClaw, etc.)
- Git (for version control)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Ways to Contribute

- Add new crisis detection indicators or response patterns
- Improve praise transformation logic
- Translate content to additional languages
- Add research references
- Improve documentation

## License

MIT License — see [LICENSE](LICENSE) for details.

## Acknowledgments

This project is built on the foundational work of researchers and practitioners dedicated to mental health and crisis intervention:

### Research Foundation

- **Muñoz et al.** — for developing the CEISS framework validating crisis intervention competencies (resilience, emotional intelligence, empathy) published in *Nature Scientific Reports*
- **Masab A. Mansoor & Kashif H. Ansari** — for pioneering AI-powered social media crisis detection research published in *Journal of Personalized Medicine*
- **Lin et al.** — for advancing digital phenotyping as a non-contact behavioral crisis detection method published in *BMC Psychology*
- **Dr. David D. Burns & Dr. Aaron T. Beck** — for the cognitive behavioral therapy framework and systematic classification of cognitive distortions in *Feeling Good: The New Mood Therapy*
- **Edmund J. Bourne** — for comprehensive anxiety and phobia treatment approaches in *The Anxiety and Phobia Workbook*
- **Columbia University C-SSRS Foundation** — for the standardized suicide severity rating scale
- **World Health Organization** — for the Mental Health Action Plan 2013-2030

### Community & Culture

- TRAE IDE — This project was built with TRAE IDE
- University communities that pioneered Praise Group culture
- Crisis intervention researchers and mental health advocates
- All researchers and journalists who documented these social phenomena

## Contact

**Project Maintainer**: Francis Tse

- Email: <francis.tse.mc@gmail.com>
- LinkedIn: <https://www.linkedin.com/in/francis-tse-6a399a47/>

## Disclaimer

**IMPORTANT: This toolbox provides AI-powered support, NOT professional counseling.**

This tool is designed to supplement, not replace, professional mental health services. The automated detection and response systems may produce incorrect assessments, inappropriate responses, or miss genuine crises. 

**See [DISCLAIMER.md](DISCLAIMER.md) for full details on:**
- Limitations and risks of automated mental health support
- Technical risks and potential malfunctions
- User and developer responsibilities
- Emergency resources and crisis hotlines
- Data privacy considerations

**In case of emergency, always contact professional crisis services immediately.**

## Links

- [GitHub Repository](https://github.com/francistse/mental-health-toolbox)
- [Hermes Agent](https://hermes-agent.ai/)
- [Model Context Protocol](https://modelcontextprotocol.io/)

