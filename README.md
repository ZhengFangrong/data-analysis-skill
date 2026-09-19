# Data Analysis Skill

一个面向决策的数据分析 Skill，基于 AI Agent 为 Excel / CSV 表格数据提供自动化分析，并生成离线 HTML 数据分析报告。

## 项目简介

本 Skill 主要用于解决大模型自动化数据分析中的**分析幻觉和结论不可验证**问题。

用户上传 Excel 或 CSV 文件并提出分析需求后，Skill 会根据实际数据完成数据摸底、质量检查、指标计算、异常分析和结果验证，并最终生成 HTML 分析报告。

核心设计是**多角色独立分析 + 真实性边界控制**。系统通过 Locator、Mechanism、Falsifier 和 Reviewer 四个独立角色，从不同角度分析和审查数据；同时对数据来源、数字计算、证据引用和结论强度进行约束，避免模型将数据中不存在的信息或未经验证的推测写成分析结论。

当数据不足以支持进一步分析时，系统不会强行生成结论，而是降低分析层级，并在报告中明确说明当前能够回答什么、无法回答什么以及需要补充哪些数据。

## 主要能力

* 支持 Excel、CSV 等结构化表格数据分析
* 支持异动分析、用户分层、漏斗与转化、指标分析、A/B 实验、因果分析、RFM 等常见分析场景
* 通过 Locator、Mechanism、Falsifier、Reviewer 进行独立角色分析
* 对关键数字进行来源追溯和复算
* 对数据质量进行检查，避免将数据问题误判为业务问题
* 对分析结论进行分级，避免结论强度超过证据强度
* 对分析失败和数据不足进行显式降级处理
* 自动生成自包含、无需联网即可打开的 HTML 数据分析报告

## 安装

### 在 Codex 中安装

本 Skill 已发布到 GitHub，仓库根目录包含 `SKILL.md`。

仓库地址：

https://github.com/ZhengFangrong/data-analysis-skill

**在 Codex 中直接安装（推荐）**

打开 Codex（桌面版、CLI 或 IDE 扩展），新建一个会话。

直接发送：

```text
请安装 data-analysis skill，仓库来源是 https://github.com/ZhengFangrong/data-analysis-skill
```

也可以先输入：

```text
$skill-installer
```

然后将上面的仓库地址交给它。

等待安装完成。Codex 通常会自动识别新 Skill；如果输入 `$data-analysis` 后没有出现，请重启 Codex 或新建一个会话。

## 使用

安装完成后，在 Codex 中上传 Excel / CSV 文件并提出你的数据分析需求即可。

例如：

```text
请分析这份用户数据，找出近期用户流失的主要特征，并给出可验证的分析结论。
```

分析完成后，系统会生成 HTML 格式的数据分析报告。


## 参考
本项目基于开源项目修改： 
- 仓库地址：[https://github.com/xiaomaxueshufen/data-analysis](https://github.com/xiaomaxueshufen/data-analysis)
