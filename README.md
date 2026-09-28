### 你好，我是 kanuba0814

2027 届本科生，方向是 **嵌入式软件 · Linux / 网络 · 机器人感知与控制**。我做过 MCU 固件、PCB、ROS 2 导航和视觉算法，也长期自己维护服务器、代理网络和家庭网关。

我的主要开发方式是**和 AI Agent 协作**：由我定目标、定边界、做验收，Claude Code / Codex 等 Agent 在各自的 worktree 里并行实现和实验。下面每个仓库都保留了这个过程的记录，包括规则文件、实验分支、检查点、验收记录和失败记录。

## 我怎样和 Agent 协作

- **写合同，而不是写叙述。** 交给实现 Agent 的任务包含 Outcome、Binding decisions、验收矩阵、下游消费方验证和停止条件；用户中途补充的要求按合同增量处理。→ [agent-workflow](https://github.com/kanuba0814/agent-workflow)
- **用证据改规则。** 我审计过自己的会话记录：实现 Agent 30 次运行中有 27 次正常退出，但独立 reviewer 的 19 份结论里有 18 份给出了 blocker。于是改了交接协议，并给提示词加上回归检查。
- **并行但隔离。** 一个实验一个 worktree，同一时刻只有一个仿真所有者，不碰别人未提交的文件，高风险改动前先打 checkpoint。→ [soarm-car](https://github.com/kanuba0814/soarm-car)（36 条分支、22 个检查点）
- **硬件安全优先。** 同一时刻只有一个主会话能驱动机械臂，子 Agent 只做只读分析；测试数据只认日志；出现故障后建立持久运动锁。→ [puzzle-arm](https://github.com/kanuba0814/puzzle-arm)
- **诚实报告。** 没验证的就写“未验证”，失败的实验保留 ABORTED 记录。

## 机器人与嵌入式

| 项目 | 简介 |
|---|---|
| [soarm-car](https://github.com/kanuba0814/soarm-car) | 家庭服务机器人：FAST-LIO + ICP 定位、Nav2 Smac + 全向 MPPI 导航、RGB-D 视觉定位、房间搜索、语义记忆（ROS 2 Humble） |
| [NanoSoul](https://github.com/kanuba0814/NanoSoul) | ESP32-P4 桌面陪伴机器人：本地人脸检测约 8 fps、10 Hz 九状态决策、语音对话、三轮全向底盘、四层载板（团队参赛作品） |
| [puzzle-arm](https://github.com/kanuba0814/puzzle-arm) | 电赛 E 题：视觉识别 + 拼图求解 + SO-101 五轴 IK 抓放，实机拼装位置偏差 1.0–3.6 mm |
| [raicom-2026-sim](https://github.com/kanuba0814/raicom-2026-sim) | 睿抗 2026 工业组（全国三等奖）：工位视觉、圆台停靠、速度闸门与健康看门狗，230 个测试 |
| [cam-imu-sync](https://github.com/kanuba0814/cam-imu-sync) | 相机 / IMU 确定性时间同步：Kalibr timeshift 跨启动极差从 972 ms 降到 2.48 ms |
| [ORB_SLAM3_ROS2](https://github.com/kanuba0814/ORB_SLAM3_ROS2) | ORB-SLAM3 ROS 2 封装的 fork：107 个提交，修复 H30 IMU 单目惯性模式的稳定性问题 |
| [pushWegit](https://github.com/kanuba0814/pushWegit) | 学习 ESP-IDF / LVGL 时的小练习：ESP32-P4 舵机送料机构 |
| [kicad-headless](https://github.com/kanuba0814/kicad-headless) | （已搁置）KiCad 10 源码编译与 PNS 布线补丁，按 scout → oracle → worker 三段式推进到 Patch 4 |

## AI Agent 工具

| 项目 | 简介 |
|---|---|
| [agent-workflow](https://github.com/kanuba0814/agent-workflow) | 我的多模型 Agent 配置：角色分工、执行合同、权限与审计扩展、双模式安装与验证 |
| [pi-truenas](https://github.com/kanuba0814/pi-truenas) | Pi 的 TrueNAS SCALE JSON-RPC 扩展 |

## 应用、数据与基础设施

| 项目 | 简介 |
|---|---|
| [webanki](https://github.com/kanuba0814/webanki) | 自托管、兼容 Anki 的间隔重复 PWA（Go + Svelte，FSRS / SM-2，WebAuthn） |
| [LocalCaption](https://github.com/kanuba0814/LocalCaption) | 离线 OpenVINO 字幕：Whisper 识别 + NLLB 翻译 + mpv 边播边出字幕 |
| [learnhub](https://github.com/kanuba0814/learnhub) | 学习资源管理：SQLite + sqlite-vec 语义检索、RAG 问答、MCP 服务器 |
| [atrading](https://github.com/kanuba0814/atrading) · [triml](https://github.com/kanuba0814/triml) | 加密货币数据湖与研究平台 · DeepLOB 订单簿研究基线（不连接交易账户） |
| [familygate](https://github.com/kanuba0814/familygate) | OpenWrt 家长控制网关：C++17 核心 + root allowlist Broker + 隔离 VM 测试环境 |
| [homelab-infra](https://github.com/kanuba0814/homelab-infra) | ImmortalWrt 网关镜像、Prometheus / Grafana 监控、Podman Quadlet、rclone 自动备份 |

## 技能

C / C++ · ESP-IDF / FreeRTOS · ROS 1 / ROS 2 · Nav2 · FAST-LIO · ORB-SLAM3 · OpenCV · KiCad · Python · TypeScript · Go · Docker / Podman · OpenWrt · Linux 网络
