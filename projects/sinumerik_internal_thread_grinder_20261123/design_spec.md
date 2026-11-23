<!-- ppt-master-schema: design-spec/v1 -->
# sinumerik_internal_thread_grinder - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | sinumerik_internal_thread_grinder_20261123 |
| Canvas Format | PPT 16:9 (1280×720) |
| Page Count | 10 |
| Primary Language | zh-CN |
| Target Audience | 数控机床客户、工艺工程师、现场操作人员及售前/售后技术支持团队，需要快速了解该数控内螺纹磨床 HMI 系统的核心功能与操作框架 |
| Communication Intent | 以 10 页篇幅系统介绍数控内螺纹磨床（型号 TEST，软件版本 3.29.0）HMI 软件的界面导航、核心加工能力（砂轮修整、自动/手动对刀、多级工艺磨削、8 项磨削扩展功能）与运维保障体系，帮助受众快速建立完整产品认知 |
| Desired Audience Outcome | 受众能在短时间内看懂机床 HMI 的界面架构与核心工艺亮点，认可系统的专业性与易用性，并明确日常加工操作与运维管理的关键入口 |
| Core Message / Ask / Action | 基于 SINUMERIK 平台的数控内螺纹磨床 HMI 3.29.0，将“修整—对刀—磨削—扩展工艺—统计运维”集成为直观统一的操作体系，兼顾高精度内螺纹加工与高效现场运维 |
| Delivery Context | 主要为有主讲人的产品介绍、客户培训或技术交流演示（10 页，约 10–15 分钟）；次要为会后可供独立翻阅的产品功能概览材料 |
| Artifact Afterlife | 作为产品对外宣讲、新操作员/客户上机培训以及内部技术交接的复用介绍材料 |
| Reading Mode | balanced |
| Content Strategy | balanced default |
| Design Style | 工业精密青 · soft-rounded |
| AI Image Acquisition Path | not applicable |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — final Stage-2 proactive policy |
| Custom Animations | disabled — final Stage-2 proactive policy |
| Narration Audio | disabled — final Stage-2 proactive policy |
| Created Date | 2026-11-23 |

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 48px (top/bottom/left/right) |
| Content Area | 1184 × 624 (x=48..1232, y=48..672) |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional
- **Mode Behavior**: 以 instructional 作为核心结构基底，按照“机床概览与导航 → 砂轮修整与滚轮齿型 → 对刀标定 → 多级工艺磨削 → 8 项扩展功能 → 运维统计与配置安全”的加工准备与执行顺序递进展开，同类界面与并列模式采用对称结构方便对照，每页用明确的功能/工序结论作标题。
- **Visual style**: soft-rounded
- **Theme**: 精密工业设备 HMI 技术宣讲与培训系统，以白色留白为基底、深青蓝为主结构色、柔和圆角容器衬托 800×600 原生实机界面
- **Tone**: 专业、清晰、克制、工程可信

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #FFFFFF | 主画布底色，保证清晰投影与浅色 HMI 截图自然融合 |
| Secondary background | #F2F5F8 | 卡片浅衬底、流程区与参数表格斑马纹底色 |
| Primary | #0F3D4C | 深青蓝主结构色，用于标题、封面/收尾主色块及主流程节点 |
| Accent | #00879E | 工业青强调色，用于关键参数高亮、激活软键与流程图主路径 |
| Secondary accent | #D97706 | 琥珀预警/边界强调色，用于权限警示、互斥约束与关键标定提示 |
| Body text | #16202A | 主正文与数据数值文本 |
| Secondary text | #52606D | 图注、辅助说明、页眉标识与页脚文本 |
| Divider | #D9E2EC | 表格边框、模块分割线与卡片描边 |

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | 工业黑体无衬线，醒目稳重 | SimHei | Arial | sans-serif |
| Body | 现代中性人文无衬线，屏幕清晰易读 | Microsoft YaHei | Arial | sans-serif |

- **Title stack**: SimHei, Arial, sans-serif
- **Body stack**: Microsoft YaHei, Arial, sans-serif

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 24 |
| Title | 42 |
| Subtitle | 32 |
| Lead | 28 |
| Annotation | 18 |
| Footnote | 15 |
| Display | 56 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: 顶部结论标题与页码锚点先行，左侧或上方建立工艺逻辑骨架，右侧或下方以柔和圆角屏幕框完整呈现 4:3 原生 HMI 截图，底部保持统一页脚与图注留白。
- **Composition tendency**: 非对称图文分栏与双屏对照为主，穿插三柱/四象限功能矩阵与原生流程拓扑，避免每页同质化均分卡片墙。
- **Cross-page continuity**: 统一的圆角设备屏幕边框（`rx="10"`）与顶部工业青序号胶囊贯穿全篇，在修整—对刀—磨削主流程页复用一致的步骤指示语言。
- **Spacing posture**: variable by page rhythm（信息页结构紧凑对齐，呼吸页留出充裕负空间突出核心界面与原理）。
- **Spacing anchors**: page margin 48px, block gap 20px, column gutter 24px, corner radius 10px, body leading 34px

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 2

| Icon Path | Suitable Scenarios |
| --- | --- |
| `tabler-outline/home-2` | |
| `tabler-outline/settings-2` | |
| `tabler-outline/adjustments-alt` | |
| `tabler-outline/target-arrow` | |
| `tabler-outline/crosshair` | |
| `tabler-outline/shield-lock` | |
| `tabler-outline/key` | |
| `tabler-outline/chart-bar` | |
| `tabler-outline/clock-2` | |
| `tabler-outline/database-edit` | |
| `tabler-outline/refresh` | |
| `tabler-outline/alert-triangle` | |
| `tabler-outline/help-circle` | |
| `tabler-outline/layers-intersect` | |
| `tabler-outline/tool` | |
| `tabler-outline/cpu` | |
| `tabler-outline/arrows-exchange` | |
| `tabler-outline/circle-check` | |
| `tabler-outline/gauge` | |
| `tabler-outline/list-check` | |
| `tabler-outline/device-desktop-analytics` | |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P06 | table | metric_table | Compare the four sequential grinding stages (rough, semi-finish, finish, final) across direction, passes, infeed, dressing frequency, and head speed |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| image_001_17.png | 800×600 | 4:3 | P01 欢迎页主视觉实机界面展示 | Product Screenshot | 右侧圆角屏幕框完整呈现欢迎页软键与机床标识 | no-crop | user | Existing | section_9_files/image_001.png：TEST 数控内螺纹磨床欢迎页实机截图 | none | hero_page |
| image_002_13.png | 800×600 | 4:3 | P02 磨削参数界面与底部水平软键导航展示 | UI Screenshot | 右侧居中完整展示底部导航软键与参数区 | no-crop | user | Existing | section_9_files/image_002.png：用户界面底部水平软键导航截图 | none | local |
| image_001_9.png | 800×600 | 4:3 | P03 修整主界面展示 | UI Screenshot | 右侧设备框完整呈现粗修/精修参数区 | no-crop | user | Existing | section_3_files/image_001.png：砂轮修整主界面实机截图 | none | local |
| image_003_8.png | 800×600 | 4:3 | P04 双圆弧齿形参数界面展示 | UI Screenshot | 左侧卡片内完整呈现哥特式双圆弧齿形与三列参数表 | no-crop | user | Existing | section_6_files/image_003.png：双圆弧齿形参数界面截图 | none | local |
| image_001_12.png | 800×600 | 4:3 | P04 单滚轮/插补滚轮标定界面展示 | UI Screenshot | 右侧卡片内完整呈现单滚轮参数与接触坐标 | no-crop | user | Existing | section_4_files/image_001.png：插补修整滚轮参数界面截图 | none | local |
| image_001_13.png | 800×600 | 4:3 | P05 自动对刀内滚道（接近开关）界面展示 | UI Screenshot | 下半区左侧完整对比展示内滚道测量界面 | no-crop | user | Existing | section_5_files/image_001.png：自动对刀-内滚道结构界面截图 | none | local |
| image_002_9.png | 800×600 | 4:3 | P05 自动对刀反向孔（测头）界面展示 | UI Screenshot | 下半区右侧完整对比展示反向孔测量界面 | no-crop | user | Existing | section_5_files/image_002.png：自动对刀-反向孔结构界面截图 | none | local |
| image_001_8.png | 800×600 | 4:3 | P06 工艺参数表界面展示 | UI Screenshot | 左侧/右侧完整展示四道工序工艺参数表 | no-crop | user | Existing | section_2_files/image_001.png：粗磨/半精磨/精磨/终磨工艺界面截图 | none | local |
| image_001_5.png | 800×600 | 4:3 | P07 环形槽磨削扩展功能界面展示 | UI Screenshot | 下方左侧展示最多 4 组环形槽参数与状态界面 | no-crop | user | Existing | section_13_files/image_001.png：环形槽磨削界面截图 | none | local |
| image_004_3.png | 800×600 | 4:3 | P07 反向孔倒角扩展功能界面展示 | UI Screenshot | 下方右侧展示反向孔倒角参数与补偿界面 | no-crop | user | Existing | section_13_files/image_004.png：反向孔倒角界面截图 | none | local |
| image_006_2.png | 800×600 | 4:3 | P08 分段补偿中径/导程界面展示 | UI Screenshot | 右侧上方展示分段补偿终点与补偿量列表 | no-crop | user | Existing | section_13_files/image_006.png：分段补偿界面截图 | none | local |
| image_007_2.png | 800×600 | 4:3 | P08 空运行热机界面展示 | UI Screenshot | 右侧下方展示 Z/X 轴往复热机参数界面 | no-crop | user | Existing | section_13_files/image_007.png：空运行热机界面截图 | none | local |
| image_001_16.png | 800×600 | 4:3 | P09 加工统计与修整轮生命周期界面展示 | UI Screenshot | 上半区左侧展示按砂轮序号统计与修整轮计数 | no-crop | user | Existing | section_8_files/image_001.png：加工统计界面截图 | none | local |
| image_001_11.png | 800×600 | 4:3 | P09 参数备份恢复界面展示 | UI Screenshot | 上半区右侧展示备份/恢复/加工模式界面 | no-crop | user | Existing | section_31_files/image_001.png：参数备份恢复界面截图 | none | local |
| image_001_15.png | 800×600 | 4:3 | P10 机床配置口令挑战码界面展示 | UI Screenshot | 左侧/右侧完整展示制造商挑战码保护界面 | no-crop | user | Existing | section_7_files/image_001.png：机床配置口令挑战码界面截图 | none | local |

## IX. Content Outline

### Part 1: 系统概览与操作导航

#### Slide 01 - 封面：TEST 数控内螺纹磨床 HMI 3.29.0
- **Audience move**: 初识产品定位 → 建立“SINUMERIK 平台全流程一体化内螺纹磨削系统”的第一印象
- **Relationships**: 主标题与副标题构成核心标识；五大核心工序标签呈顺序链路（修整 → 对刀 → 磨削 → 扩展 → 运维）；右侧欢迎页截图为系统实机锚点
- **Composition**: 左文右屏非对称封面：左侧深青蓝主块承载型号徽章、主标题与五步工序链路；右侧圆角设备框完整展示欢迎页实机界面
- **Title**: TEST 数控内螺纹磨床 HMI 3.29.0 系统介绍
- **Core message**: 基于 SINUMERIK 平台，将“修整—对刀—磨削—扩展工艺—统计运维”集成于统一直观的操作界面，兼顾高精度加工与现场运维。
- **Cover impact**: 型号 `TEST` · 软件版本 `3.29.0` · 18 项原生 HMI 界面与工艺能力全景解析
- **Content**:
  - 平台与版本：机床型号 `TEST` · 机床名称 `数控内螺纹磨床` · 软件版本 `3.29.0`
  - 核心价值链路：砂轮修整 → 自动/手动对刀 → 多级工艺磨削 → 8 项扩展加工 → 统计寿命与备份运维
  - 适用对象：机床客户 · 工艺工程师 · 现场操作人员 · 技术支持团队
- **Images**: `image_001_17.png`（欢迎页主界面）

#### Slide 02 - 双层界面导航与操作面板联动
- **Audience move**: 不熟悉操作入口 → 掌握“欢迎页 + 用户界面 + 面板按键 + HELP”四位一体的操作逻辑
- **Relationships**: CUSTOM 欢迎页与用户界面为层级包含（parent）；底部 4 大加工入口呈并列关系；面板功能键按执行优先级排序（order）
- **Composition**: 左侧双层导航结构图 + 面板优先级序列；右侧展示用户界面实机导航截图
- **Title**: 双层菜单架构与面板联动：一眼直达核心加工与运维入口
- **Core message**: 按 CUSTOM 键直达欢迎页，底部软键一键切换四大加工页面，配合面板功能键优先级与 HELP 即时帮助，大幅降低上手门槛。
- **Content**:
  - **欢迎页入口（CUSTOM 键）**：出厂信息 / 备份恢复 / 配件寿命 / 加工统计 / `▷` 扩展进入机床配置；底部“用户界面”进入加工区
  - **四大加工软键**：磨削参数 · 工艺参数 · 修整参数 · 自动对刀（含“返回”回欢迎页）
  - **循环启动优先级**：空运行使能 > 自磨夹具 > 修整 > 自动对刀 > 手动对刀 > C 轴旋转 > 功能键全灭执行磨削（“退刀”可安全中止退出）
  - **即时帮助**：任意页面选中参数按 `HELP` 键，下半屏直接显示参数说明与修改权限
- **Images**: `image_002_13.png`（磨削参数与底部水平软键导航）

### Part 2: 加工准备：砂轮修整与精确对刀

#### Slide 03 - 砂轮修整体系与两轴位置标定
- **Audience move**: 了解需要修整 → 理解 4 种修整触发时机、2 类修整器及免重对刀自动补偿机制
- **Relationships**: 4 种修整方式按触发时机对比（contrast）；X-W 插补与成型X 为两类并列修整路径；修整标定公式与自动补偿构成因果支撑（link）
- **Composition**: 左上 4 种修整方式精简对照 + 左下两类修整器与标定公式卡片；右侧完整呈现修整主界面截图
- **Title**: 四大修整触发机制与两类修整器，覆盖新旧砂轮全生命周期
- **Core message**: 支持新/旧砂轮单独修整及磨削中/按件数自动修整，每次修整后自动更新砂轮直径并补偿磨削位置，无需重新对刀。
- **Content**:
  - **4 种修整方式**：新砂轮修整（外圆逐层修出完整齿形，按 `(新砂轮直径 - 最大磨削直径)/2` 自动算次数） · 旧砂轮修整 · 磨削中修整（只做精修） · 按件数修整
  - **2 类修整器**：`X-W`（碟形单/方/双滚轮两轴插补修整） vs `成型X`（成型滚压轮直线复制齿形）
  - **位置标定与防误改**：`修整中心距 = |X1 + D1/2 + D2/2|` · `修整中心 = (Z1 + Z2)/2` · 参数旁设默认闭合的锁定开关
  - **安全上下限**：低于最小磨削直径自动报警；新砂轮修至最大磨削直径确保进入内孔
- **Images**: `image_001_9.png`（修整主界面）

#### Slide 04 - 多齿型兼容、双圆弧自动计算与滚轮配置
- **Audience move**: 仅知修整概念 → 看清系统可修出三角、梯形、双圆弧、行星齿等多种高难度齿型并支持多线高效修整
- **Relationships**: 三角/梯形/双圆弧/多线修整为并列齿型能力（membership）；双圆弧计算公式与“初始/调整/当前”三列修正为因果闭环（link）；左图齿型与右图滚轮为互锁配合关系
- **Composition**: 上方 3 枚精炼齿型能力标签卡（含双圆弧公式）；下方双屏并排展示双圆弧齿型界面与单滚轮标定界面（breathing 留白节奏）
- **Title**: 兼容三角、梯形与哥特式双圆弧齿型，支持多线高效修整
- **Core message**: 内置三角、梯形（含戴帽）与滚珠丝杠双圆弧齿型计算模型，并可选配多线多牙修整与四种修整轮几何配置。
- **Content**:
  - **三角 / 梯形齿型**：普通单段斜面 / 扩展上下双段不同角度斜面；梯形另支持“戴帽”中径定义及平顶/锥顶模式
  - **双圆弧齿型（滚珠丝杠/螺母）**：支持“初始 + 调整 = 当前”闭环修正；打开自动计算后按 `圆弧半径 = 标准切换 × 钢球直径 / 2` 与 `水平偏心 = (圆弧半径 - 钢球直径/2) × sin(接触角)` 自动生成（标准切换推荐 `1.11`，接触角 `45°`）
  - **多线与附加齿型**：选配多线修整（牙数 / 间隔螺距 0~5 / 齿高补偿 -1~1mm），另可开放行星齿与平面磨修整
  - **4 种修整轮配置**：单滚轮（单圆弧） · 方滚轮（厚度 + 左右圆弧） · 双滚轮（间距中心） · 滚压轮（齿高判定）
- **Images**: `image_003_8.png`（双圆弧齿形界面） · `image_001_12.png`（单滚轮参数界面）

#### Slide 05 - 手动插补与六大自动对刀测量体系
- **Audience move**: 担心内孔对刀难 → 确认既有安全的手动插补/静止对刀，更有覆盖内滚道与反向孔的全自动找正能力
- **Relationships**: 手动对刀与自动对刀为双路径并列对比（contrast）；自动对刀内部分为“内滚道（接近开关）”与“反向孔（测头 4 模式）”树状分支（parent）
- **Composition**: 上方双路径对比与手动/自动分支要点；下方左右并置内滚道与反向孔自动对刀实机界面
- **Title**: 双路径精准对刀：手动插补微调配合六大自动测量模式
- **Core message**: 精准测定 `加工起始角.C` 与 `初始接触.X`，通过内滚道接近开关与测头多模式自动复测，兼顾首件精度与批量节拍。
- **Content**:
  - **手动对刀与批量保护**：支持插补对刀与静止对刀；DRF 手轮微调落槽后按“退刀”即记数退出；区分“首件/不是首件”，非首件保持 `初始接触.X` 锁定尺寸一致
  - **自动对刀——内滚道（接近开关）**：伸入内孔沿 Z 向探测螺纹槽两侧牙侧取中点；碰牙顶自动退开平移重试（最多 5 次）
  - **自动对刀——反向孔（测头）**：支持测量反向孔（圆形/腰形、常规/只测C）、测量右端台阶、测量右端孔、外圆面右端反，支持孔周步距探测与超阈值（默认 0.05mm）停机防撞
  - **精准偏刀修正**：标定 `测量水平距.Z = |Z1 - 测头半径 - Z2|`，磨削后可在 `对刀结果调整` 叠加补偿，无需重标机构
- **Images**: `image_001_13.png`（自动对刀-内滚道界面） · `image_002_9.png`（自动对刀-反向孔界面）

### Part 3: 核心磨削工艺与专机扩展能力

#### Slide 06 - 四级工艺磨削表与六类偏差闭环补偿
- **Audience move**: 理解对刀准备 → 掌握粗磨到终磨的工艺编排与磨削后尺寸微调机制
- **Relationships**: 四道工序（粗磨 → 半精磨 → 精磨 → 终磨）呈严格顺序递进（order）；“测量偏差 → 对应补偿参数”呈一一对应映射（link）
- **Composition**: 左侧上方嵌入四级工艺参考参数表（`metric_table`）+ 下方 6 类磨削后偏差调整映射；右侧完整呈现工艺界面实机截图
- **Title**: 粗磨至终磨四级工艺联动，实现尺寸与螺距全链路闭环
- **Core message**: 区分单件调整与批量生产双套独立工艺表，四道工序逐级降速减深并支持中断续磨，测量误差一一对应直接补偿。
- **Content**:
  - **双模式工艺表**：`单件调整`（试磨）与 `批量生产`（量产）各自独立保存；支持单向/双向（双向总和或单次进刀）及工序内按次自动精修；批量模式支持指定工序/循环中断续磨
  - **磨削速度换算**：`磨削速度 = 头架转速 × 螺距 × 头数`；非恒转速模式下按线速度自动换算砂轮转速（内螺纹线速度参考 20 m/s）
  - **6 大测后补偿入口**：中径偏差 → `中径补偿` · 两侧不均 → `偏刀补偿` · 螺距累积误差 → `全长导程补偿` · 两端中径差 → `全长锥度补偿` · 局部误差 → `分段补偿` · 批量漂移 → `磨削中补偿`
- **Visualization**: `craft-stage-table` (`table/metric_table` — 粗磨 / 半精磨 / 精磨 / 终磨工艺参考示例：方向全单向，进给深度 0.04 / 0.02 / 0.01 / 0.005 mm，头架转速 50 / 40 / 30 / 30 r/min，半精/精/终循环 3 / 2 / 2，修整设定 5 / 3 / 0 / 0)
- **Native-ready**: `craft-stage-table=yes`
- **Images**: `image_001_8.png`（工艺参数表界面）

#### Slide 07 - 磨削扩展功能 (上)：四项异形与变参数加工
- **Audience move**: 了解常规内螺纹磨削 → 认识机床面对非标、多段变参数工件的专机级扩展能力
- **Relationships**: 环形槽磨削、螺距变换、反向孔倒角、变径磨削为 4 项按机床配置按需开启的平行扩展功能（membership）
- **Composition**: 上方四栏精炼能力说明卡片（含各自关键参数与操作要点）；下方左右并列展示环形槽与反向孔倒角实机截图
- **Title**: 四大专机级扩展加工能力，从容应对复杂内螺纹结构
- **Core message**: 通过机床配置按需开启右侧扩展软键，无需定制编程即可在标准界面完成环形槽、变螺距、反向孔倒角与变径磨削。
- **Content**:
  - **环形槽磨削**：磨削类型选“环形槽”进入，支持最多 4 组槽的槽数、槽距、槽升量与组间偏移，左侧实时显示已加工槽数
  - **螺距变换（单 / 多）**：支持单段“给定角度 / 终点变换”及多段变螺距分段填写角度与螺距，配合平滑轨迹消除拐点冲击
  - **反向孔倒角**：设定过渡角、倒角深度、平移角与两端预倒角；支持手动输入各 Z 坐标或首孔定位自动推算，附位置与终点微调补偿
  - **变径磨削**：设置两端无效牙角度、变径量与过渡角度，可选“每刀螺纹+变径”或“螺纹完成后单独磨变径段”
- **Images**: `image_001_5.png`（环形槽磨削界面） · `image_004_3.png`（反向孔倒角界面）

#### Slide 08 - 磨削扩展功能 (下)：分段补偿、热机与自磨夹具
- **Audience move**: 关注特殊工况 → 掌握长螺纹局部纠偏、机床热稳定性控制与夹具在线修整能力
- **Relationships**: 分段补偿、空运行热机、自磨夹具、DIY 工艺为 4 项精度保障与定制维护能力（membership）；分段补偿与倒角/变径/变螺距互斥（contrast）
- **Composition**: 左侧三张精炼能力卡片（含互斥与操作提示胶囊）；右侧上下两张实机截图呼吸式排布（breathing 节奏）
- **Title**: 分段精度纠偏与机床自维护功能，守住长螺纹与批量一致性
- **Core message**: 从分段中径/导程微调、空载往复热机到夹具自磨与 DIY 程序接口，全面消除长行程误差、温漂与装夹偏心。
- **Content**:
  - **分段补偿中径/导程**：按检测报告从右端起逐段输入终点 Z、中径与导程补偿量，仅自动磨削生效；注意同时开启反向孔倒角、变径或变螺距时不执行分段补偿
  - **空运行热机**：设置 Z/X 轴安全往复范围、转速与速度，开启使能后优先执行空载热机消除冷机温漂（热机后务必关闭使能）
  - **自磨夹具**：支持在线设定夹具磨削左右端、接触位置与修整参数，修整装夹基准保障同心度（完成后务必关闭开关）
  - **DIY 工艺模式**：支持按用户自定义 DIY 程序执行特种工序（启用 DIY 时标准工艺表呈只读保护）
- **Images**: `image_006_2.png`（分段补偿界面） · `image_007_2.png`（空运行热机界面）

### Part 4: 运维追溯、安全保护与系统总结

#### Slide 09 - 加工统计、配件寿命预警与参数备份恢复
- **Audience move**: 聚焦单件加工 → 建立车间批量生产的耗材追溯、寿命防呆与数据安全习惯
- **Relationships**: 加工统计、配件寿命、参数备份恢复三大运维模块呈并列支撑关系（membership）；备份/恢复执行前后的模式切换（备份/恢复 ↔ 加工）为严格顺序约束（order）
- **Composition**: 上方左右并列展示加工统计与参数备份恢复实机截图；下方三列结构化运维要点卡片对应承接
- **Title**: 数字化生产追溯与防呆备份，保障车间连续稳定运行
- **Core message**: 自动统计砂轮加工件数与修整轮损耗，配件超寿启动暂停预警，并提供全量及最多 790 个自定义变量的参数备份与 USB 恢复。
- **Content**:
  - **加工统计（钥匙开关 3 档）**：按砂轮序号自动统计批量生产完成件数与更换日期；修整轮生命周期区记录已修整次数与累计修整量，超限提示更换
  - **配件寿命与滚轮记录**：设定寿命与报警阈值，超限启动程序即暂停提醒；更换后点击 `↺` 清零并记录时间，支持查阅历次滚轮更换编号与日期
  - **参数备份与恢复（用户口令）**：支持全部参数或自定义变量列表（如 `PAR_DEMO.TXT`，最多 790 个参数，含注释/空行需准确填写总行数、`*` 标识字符串）；支持后部 USB（`//DEV_3`）恢复；完成后必须将模式改回 **加工**
- **Images**: `image_001_16.png`（加工统计界面） · `image_001_11.png`（参数备份恢复界面）

#### Slide 10 - 四级权限安全体系与系统价值总结
- **Audience move**: 完成系统浏览 → 明确不同岗位的操作权限边界，带走“安全可控 + 闭环高效”的系统全貌
- **Relationships**: 四级权限呈递进包含关系（order：钥匙 0 档 → 钥匙 3 档 → 用户口令 → 制造商口令挑战码）；左侧权限阶梯与右侧挑战码界面构成机制与实证映射（link）
- **Composition**: 左侧四级权限递进阶梯图 + 制造商配置边界；右侧展示机床配置挑战码界面截图，底部收束全套系统的核心闭环价值带（anchor 收尾页）
- **Title**: 四级权限隔离与挑战码配置保护，兼顾操作便捷与设备安全
- **Core message**: 从日常微调到制造商底层配置实施四级严格隔离，以挑战码防呆机制守护核心机床参数，实现高效、精准、可追溯的加工闭环。
- **Closing impact**: 一套统一 HMI，串联“精密修整—智能对刀—四级磨削—专机扩展—寿命备份—安全配置”全周期闭环，建议新设备部署后按“配置确认 → 标定试磨 → 批量运维”三步投入现场应用。
- **Content**:
  - **一级 · 钥匙开关 0 档**：日常调机权限（中径补偿、偏刀补偿、全长补偿等）
  - **二级 · 钥匙开关 3 档**：工艺与标定权限（工件、工艺表、修整、对刀参数及加工统计）
  - **三级 · 用户口令**：运维管理权限（参数备份恢复、出厂信息及机床配置入口）
  - **四级 · 制造商口令（挑战码解锁）**：控制选配功能显隐（空运行/分段补偿/螺距变换等）、机床数据重置及参数安全上下限；切勿自行篡改配置
- **Images**: `image_001_15.png`（机床配置挑战码界面）

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: 基于手册实际参数、公式与操作注意事项撰写口语化讲解词，紧扣各页实机截图重点与切换衔接，不编造手册未提及的指标
- **Total duration**: 12 分钟（10 页，平均每页约 1–1.5 分钟）
- **Notes style**: 专业清晰、讲解导向（兼具客户介绍与工艺培训实用性）
- **Presentation purpose**: 以 10 页篇幅系统介绍数控内螺纹磨床（型号 TEST，软件版本 3.29.0）HMI 软件的界面导航、核心加工能力与运维保障体系，帮助受众快速建立完整产品认知
