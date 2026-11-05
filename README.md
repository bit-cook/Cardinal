# 枢机项目计划 · Cardinal Plan

> **Everything hinges on it.** 万事，系于此枢。

本仓库是 **枢机（Cardinal）项目** 的计划与文档站：交接文档、部署手册、对话全记录。
**实现代码在另一个仓库：[bit-cook/shuji](https://github.com/bit-cook/shuji)**（命令路由、心跳 Sidecar、部署清单、CI）。

- **枢** = 控制面：命令由此下达，数据由此回报，一切绕它运转
- **机** = 机器 / 机关 / 机制：Agents（机器）、命令路由（机关）、触发与执行
- 中文「枢机」（户枢 + 弩机）与英文 **Cardinal**（拉丁语 cardo，门轴）是词源上的双胞胎：门轴 → 关键
- 徽记为红衣凤头鸟（Cardinal bird，因枢机主教红袍得名）——众仆之长，服务于唯一的主宰

## 本仓库（计划与文档）

| 文件 | 说明 |
| --- | --- |
| `index.html` | 官网首页（GitHub Pages，单文件、零依赖） |
| `docs/index.html` | 文档中心（阅读顺序 + 全部文档导航） |
| `docs/handover.html` | 给其他 Agent 的交接文档（10 节） |
| `docs/runbook.html` | 多 Agent 舰队部署手册（快速开始 + 阶段 00–10） |
| `docs/record.html` | Agenos 对话全记录（六阶段 + 每阶段结论） |
| `docs/docs.css` | 文档站共享样式 |
| `logo.svg` | 主徽标（红衣凤头鸟，透明底） |
| `favicon.svg` | 徽标暗色圆角底版（favicon / 小尺寸） |

## 实现在别处

[**bit-cook/shuji**](https://github.com/bit-cook/shuji) — 枢机的软件实现：

- `packages/wechat-bridge` — 命令路由（Node，零依赖）：白名单、六条命令协议、危险命令二次确认、企业微信回调加解密、JSONL 审计
- `packages/hermes-sidecar` — Hermes 心跳 Sidecar（Python 标准库）：generic 协议心跳、重试退避、systemd 加固单元
- `deploy/` — docker-compose、systemd 单元、环境变量模板、安装脚本
- `test/` — Mission-Control 测试桩 + T1–T8 端到端验收脚本

## 项目文档（GitHub Pages 托管）

- [文档中心](https://osome.work/cardinal-plan/docs/) — 先读交接文档 → 再按手册执行 → 查全记录溯源
- [给其他 Agent 的交接文档](https://osome.work/cardinal-plan/docs/handover.html)
- [多 Agent 舰队部署手册（11 阶段）](https://osome.work/cardinal-plan/docs/runbook.html)
- [Agenos 对话全记录](https://osome.work/cardinal-plan/docs/record.html)

原始发布版（豆包页面）：[交接文档](https://4m9692y3g6zdz.doubao.link/app/app_17hb8aveamv) · [部署手册](https://4m9692y3g6zdz.doubao.link/app/app_17hb39p9gdc) · [对话全记录](https://4m9692y3g6zdz.doubao.link/app/app_17hb8avchb0)

## 最高原则

整个 Agent 世界只服务用户一个人——唯一管理员、唯一主宰。命令入口白名单，危险操作二次确认，端口不暴露公网。
