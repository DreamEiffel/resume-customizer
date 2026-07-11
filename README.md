# 🎯 Career Coach — 你的专属求职军师

> **诊断 → 优化 → 面试**，一站式搞定求职全链路。

[![Skill Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](https://github.com/yourusername/career-coach)
[![Hermes Compatible](https://img.shields.io/badge/Hermes-Compatible-green.svg)](https://hermesapp.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📌 一句话介绍

**Career Coach** 是一个帮助求职者（特别是学生）深度优化简历、精准匹配岗位、准备面试的 AI Skill。它像一位懂招聘的学长/学姐，手把手带你完成从“投递简历”到“拿下 offer”的全过程。

---

## ❓ 为什么需要这个 Skill？

| 你的困境 | 它能帮你什么 |
|---------|-------------|
| 海投 50 份简历，0 回复 | 逐项诊断你与目标岗位的差距，告诉你“缺什么、怎么补” |
| 简历只会写“我负责了数据清洗” | 强制用 **STAR 法则** + **量化数据** 改写，让经历有说服力 |
| 一家公司投多个岗位，不知怎么改 | 生成 **3 种不同人设** 的简历描述，任你选择 |
| 面试自我介绍像背课文 | 把书面简历自动转成 **250 字口语稿**，1 分钟讲完重点 |
| 不知道面试官会问什么 | 根据岗位 JD 生成 **3 道模拟面试题** + 回答框架 |

---

## 🧠 核心工作流程（5 步闭环）

| 阶段 | 做什么 | 输出物 |
|------|--------|--------|
| **0. 信息确认** | 读取简历附件 + JD，提取关键信息 | 《信息确认表》（等待用户确认） |
| **1. 人岗诊断** | 逐项对比 JD 要求与用户背景 | 硬技能/软技能/致命伤 三张诊断表 |
| **2. 三案生成** | 生成 3 种差异化简历描述 | A(技术硬核) / B(业务价值) / C(成长潜力) |
| **3. 迭代修改** | 根据用户反馈定向调整 | 精准响应的修改版本 |
| **4. 面试交付** | 转化成口语稿 + 模拟面试题 | 1分钟自我介绍稿 + 3道面试押题 |

---

## 🚀 快速开始

### 前置条件
- 已安装 [Hermes Desktop](https://hermesapp.com) 或任何支持 Skill 的 Agent（Claude Code / CodeBuddy 等）
- 准备好你的 **简历文件（.pdf/.docx/.txt）** 和 **目标岗位 JD（招聘描述）**

### 安装步骤

#### 方式一：通过 Hermes Desktop GUI（推荐）
1. 打开 Hermes Desktop → 左侧点击 **Skills** 图标
2. 点击 **「Import Skill」**
3. 将下方 `SKILL.md` 内容粘贴到弹出的文本框 → 保存

#### 方式二：手动放置文件夹
# 进入 Hermes Skills 目录（macOS）
cd ~/Library/Application\ Support/Hermes/skills/

# 或者（Windows）
cd C:\Users\你的用户名\AppData\Roaming\Hermes\skills\

# 创建 Skill 文件夹
mkdir career-coach
cd career-coach

# 创建 SKILL.md 文件并粘贴内容
touch SKILL.md

**重启 Hermes Desktop（桌面端必须重启才能识别新 Skill）

使用示例
在 Hermes 对话框中输入：

text
帮我优化简历，准备面试。
这是我的简历：[上传附件]
目标岗位 JD：[粘贴招聘描述]


适用人群
🎓 在校大学生：正在找实习/校招，需要优化简历和准备面试

🧑‍💻 转行求职者：需要针对目标岗位重新包装经历

📚 求职陪跑导师/助教：帮学生批量修改简历时，用 Skill 提效
