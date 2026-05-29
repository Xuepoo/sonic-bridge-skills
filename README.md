# SonicBridge Skills

[English](#english) | [简体中文](#简体中文)

---

## 简体中文

智能体音乐审美与物理转译技能库。

本仓库定义了配合 [`sonic-bridge`](https://github.com/Xuepoo/sonic-bridge) 听觉引擎使用的 AI Agent 技能描述规范，使纯文本 LLM 获得对音乐的"具身听觉"能力——包括 LRMD 协议解析、同频共听伴读与乐理情感分析。

### 技能目录

| 技能名称 | 描述 |
| :--- | :--- |
| [audio-analysis](audio-analysis/SKILL.md) | 通过 `sonic-bridge` CLI 对本地音频进行时域、频域、和弦、瞬态检测，输出 LRMD 审美报告 |

### 使用方式

将本仓库中的技能文件安装到你的 Agent 技能目录（如 `.agents/skills/` 或 `.gemini/skills/`），使 Agent 在用户播放音乐时自动调用 `sonic-bridge` 进行声学分析并生成陪伴式乐理对话。

```bash
# 示例：将 audio-analysis 技能安装到项目技能目录
cp -r audio-analysis /path/to/your-project/.agents/skills/
```

---

## English

AI Agent Music Aesthetic & Physical Translation Skills Repository.

This repository defines AI Agent skill specifications designed to work with the [`sonic-bridge`](https://github.com/Xuepoo/sonic-bridge) listening engine. It empowers pure-text LLMs with "embodied hearing" capabilities — including LRMD protocol parsing, co-listening companionship, and musicological emotional analysis.

### Skills Directory

| Skill | Description |
| :--- | :--- |
| [audio-analysis](audio-analysis/SKILL.md) | Perform temporal, spectral, harmonic, and transient analysis on local audio via `sonic-bridge` CLI, producing LRMD reports |

### Usage

Install the skill files from this repository into your Agent's skills directory (e.g., `.agents/skills/` or `.gemini/skills/`), enabling the Agent to automatically invoke `sonic-bridge` for acoustic analysis and generate companion-style musicological dialogue when users play music.

```bash
# Example: Install audio-analysis skill to project skills directory
cp -r audio-analysis /path/to/your-project/.agents/skills/
```

## License

[MIT](LICENSE)
