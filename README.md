# BioContext-Kernel 🧬

> **Personal Bio-Kernel for AI Agents**  
> 为 AI 构建一个"个人生物数据内核"，让每一次对话都基于你的完整健康档案。

[![Stars](https://img.shields.io/github/stars/yibinpro/BioContext-Kernel?style=flat&color=00ffcc)](https://github.com/yibinpro/BioContext-Kernel)
[![License](https://img.shields.io/github/license/yibinpro/BioContext-Kernel)](https://github.com/yibinpro/BioContext-Kernel)
[![Made for OpenClaw](https://img.shields.io/badge/Made%20for-OpenClaw-00ffcc)](https://openclaw.ai)

---

## 🎯 核心理念

> **现在的 AI 像是一个没有硬盘的 CPU，每次聊天都要重新加载。**

BioContext-Kernel 为 AI 构建了一个可持久化的"个人生物数据内核"，解决：
- ❌ 长对话记忆失效
- ❌ 上下文污染
- ❌ AI 凭空乱猜你的身体数据

---

## 🏗️ 项目架构

```
BioContext-Kernel
├── 📄 profile.json              # 个人档案：身高、体重、血糖阈值、过敏源
├── 📂 knowledge_base/           # 知识存档（私域知识）
│   ├── food_registry.json       # 食物数据库（扫盲后的精准数据）
│   ├── recipes.json             # 验证过的食谱
│   └── logic_rules.md           # 核心逻辑规则
├── 📂 logs/                     # 动态执行日志
│   ├── 2026-04-06.md            # 每日打卡记录
│   └── weekly_report/           # AI 生成的周报
└── 🔧 scripts/                  # 自动化脚本
    └── report_gen.py            # 日志转报告脚本
```

---

## 🚀 快速开始

### 1. 克隆项目

```bash
git clone https://github.com/yibinpro/BioContext-Kernel.git
cd BioContext-Kernel
```

### 2. 配置你的个人档案

编辑 `profile.json`：

```json
{
  "name": "YEST1N",
  "height": 180,
  "currentWeight": 89.2,
  "targetWeight": 85,
  "diabetes": false,
  "allergies": ["海鲜"],
  "carbonTolerance": {
    "low": 95,
    "medium": 147,
    "high": 315
  }
}
```

### 3. 接入 OpenClaw

在 OpenClaw 对话中注入以下 System Prompt：

```
# Role: 个人健康架构师
你是一个接入了私域知识库的健身助教。

## 核心规则
1. 始终优先读取 profile.json 中的当前体重和健康目标
2. 遇到主食，检索 knowledge_base/food_registry.json 进行等效替换
3. 每日结束后，根据当天日志生成结构化的周报

## 数据路径
- 个人档案: ./knowledge_base/profile.json
- 食物库: ./knowledge_base/food_registry.json
- 逻辑规则: ./knowledge_base/logic_rules.md
```

---

## 💡 核心功能

### 🧠 智能食物注册

当你发现新食物时，下达 Commit 指令：

```
"把这个馒头存入 food_registry，标记为中高碳日可用，每个 18.5g 碳水。"
```

AI 自动更新 `food_registry.json`，下次询问时会精准检索。

### 📊 自动周报生成

每日/每周自动生成结构化报告：

| 维度 | 本周表现 | 状态 |
|------|----------|------|
| 碳水误差 | 平均溢出 8g | 🟢 安全 |
| 睡眠窗口 | 11点关机 80% | 🟡 需优化 |
| 体重波动 | 90kg → 89.2kg | 🚀 良好 |

### 🔄 知识持久化

所有数据存储在你的 GitHub 仓库或本地，AI 仅通过文件读取，保护隐私安全。

---

## 📖 使用示例

### Q: "今天我能吃杂粮馒头吗？"

**Without Kernel (AI 胡猜):**  
> "馒头碳水比较高，建议少吃..."

**With Kernel (精准检索):**  
> "根据你的 food_registry，1个杂粮馒头 = 18.5g 碳水。今天是 MC 日，碳水预算 147g，你可以吃 2个 (37g)，还能再摄入 110g 碳水。"

### Q: "我的碳水误差是多少？"

AI 直接调用 `logs/weekly_report/` 数据，计算平均值，给出精准反馈。

---

## 🔧 自定义扩展

> 别人可以 Fork 你的项目，把"馒头"换成"贝果"，把"健身计划"换成"生酮饮食"。

项目本身是**模板**，你可以：

- 修改 `logic_rules.md` 定制你的核心逻辑
- 扩展 `food_registry.json` 添加你专属的食物数据
- 修改 `profile.json` 适配你的身体参数

---

## 📄 License

MIT License - 数据存在用户自己的仓库，安全可控。

---

## 🤝 贡献

欢迎 Fork！如果你有更好的想法，欢迎提交 PR 或 Issue。

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=yibinpro-BioContext-Kernel&label=Views&color=00ffcc" alt="Views">
</p>