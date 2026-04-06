# FitDietKernel 🥗

> **健身饮食的个人知识库**  
> 无论你用什么饮食方法，AI 都能精准帮你算

[![Stars](https://img.shields.io/github/stars/yibinpro/FitDietKernel?style=flat&color=2ecc71)](https://github.com/yibinpro/FitDietKernel)
[![License](https://img.shields.io/github/license/yibinpro/FitDietKernel)](https://github.com/yibinpro/FitDietKernel)

---

## 🎯 解决什么问题

健身最痛的点：

| 痛点 | 传统 AI | CarbonKernel |
|------|---------|--------------|
| "这个能吃吗" | "馒头碳水高，少吃" | "1个=18.5g碳水，今天MC日能吃2个" |
| "今天吃超了吗" | "大概没超吧" | "实际52g，目标147g，-95g安全" |
| "上次那个食物呢" | "抱歉我忘了" | **永远记得** |

---

## 🏗️ 项目结构

```
CarbonKernel
├── profile.json              # 你是谁：体重、目标、碳循环档位
├── knowledge_base/
│   ├── food_registry.json    # 你的食物数据库（精准碳水）
│   ├── recipes.json         # 验证过的食谱
│   └── rules.md              # 核心规则：误差控制、进食顺序
└── logs/
    ├── 2026-04-06.md         # 每日打卡
    └── weekly_report/        # AI 周报
```

---

## 🥋 支持的饮食方法

| 饮食法 | 配置示例 |
|--------|----------|
| **碳循环** | 低95g / 中147g / 高315g |
| **生酮** | 碳水<30g，脂肪>70% |
| **增肌** | 碳水400g+，蛋白200g+ |
| **减脂** | 碳水150g，蛋白180g |
| **16:8间歇断食** | 进食窗口 12:00-20:00 |

---

## 🚀 快速开始

### 1. Fork 项目

点击右上角 Fork，修改成你的数据

### 2. 配置你的档案

```json
// profile.json
{
  "name": "你的名字",
  "currentWeight": 80,
  "targetWeight": 75,
  "carbonCycle": {
    "low": 95,
    "medium": 147,
    "high": 315
  }
}
```

### 3. 接入 AI（OpenClaw 示例）

```
你是一个精准饮食教练。

规则：
1. 读 profile.json 获取我的碳水预算
2. 查 food_registry.json 计算食物碳水
3. 告诉我今天还能吃多少
```

---

## 💡 核心功能

### 🔢 精准碳水计算

```
问：今天能吃几个馒头？
答：
- 你的馒头：1个 = 18.5g 碳水
- 今天是 MC 日，预算 147g
- 已吃：65g燕麦 + 50g蓝莓 = 40g
- 剩余：147 - 40 = 107g
- 可以吃：107 ÷ 18.5 = **5.7个**
```

### 📊 误差追踪

| 周 | 平均误差 | 状态 |
|----|----------|------|
| 第1周 | +8g | 🟢 |
| 第2周 | -5g | 🟢 |
| 第3周 | +22g | 🟡 需注意 |

### 🔄 新食物注册

```
"把这个贝果存入，1个=25g碳水，早餐用"
```

AI 自动更新数据库，下次直接查。

---

## 📖 谁适合用

- 🏋️ 任何健身饮食法的人
- 🥗 碳循环 / 生酮 / 增肌 / 减脂 / 间歇断食
- 🤖 用 AI 辅助健身的人

---

## 🔧 技术细节

- 数据存本地/GitHub，隐私安全
- 纯 JSON + Markdown，无数据库
- 配合任意 AI（ChatGPT/OpenClaw/Claude）

---

## 📄 License

MIT - 你自己的数据，存在你自己的仓库。

---

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=yibinpro-FitDietKernel&label=Views&color=2ecc71" alt="Views">
</p>