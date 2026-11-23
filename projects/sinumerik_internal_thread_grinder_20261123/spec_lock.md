<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- format: PPT 16:9
- viewBox: 0 0 1280 720

## communication
- primary_language: zh-CN
- audience: 数控机床客户、工艺工程师、现场操作人员及售前/售后技术支持团队
- objective: 以 10 页篇幅系统介绍 TEST 数控内螺纹磨床 HMI 3.29.0 的界面导航、加工能力与运维体系，使受众看懂架构亮点并掌握操作与运维关键入口
- core_message: 基于 SINUMERIK 平台的数控内螺纹磨床 HMI 3.29.0，将“修整—对刀—磨削—扩展工艺—统计运维”集成为直观统一的操作体系，兼顾高精度内螺纹加工与高效现场运维
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional
- mode_behavior: 以 instructional 作为核心结构基底，按照“机床概览与导航 → 砂轮修整与滚轮齿型 → 对刀标定 → 多级工艺磨削 → 8 项扩展功能 → 运维统计与配置安全”的加工准备与执行顺序递进展开，同类界面与并列模式采用对称结构方便对照，每页用明确的功能/工序结论作标题。

## visual_style
- visual_style: soft-rounded

## colors
- background: #FFFFFF
- secondary_bg: #F2F5F8
- primary: #0F3D4C
- accent: #00879E
- secondary_accent: #D97706
- body_text: #16202A
- secondary_text: #52606D
- divider: #D9E2EC

## typography
- font_family: Microsoft YaHei, Arial, sans-serif
- title_family: SimHei, Arial, sans-serif
- body_family: Microsoft YaHei, Arial, sans-serif
- body: 24
- title: 42
- subtitle: 32
- lead: 28
- annotation: 18
- footnote: 15
- display: 56

## icons
- library: tabler-outline
- stroke_width: 2
- inventory: tabler-outline/home-2, tabler-outline/settings-2, tabler-outline/adjustments-alt, tabler-outline/target-arrow, tabler-outline/crosshair, tabler-outline/shield-lock, tabler-outline/key, tabler-outline/chart-bar, tabler-outline/clock-2, tabler-outline/database-edit, tabler-outline/refresh, tabler-outline/alert-triangle, tabler-outline/help-circle, tabler-outline/layers-intersect, tabler-outline/tool, tabler-outline/cpu, tabler-outline/arrows-exchange, tabler-outline/circle-check, tabler-outline/gauge, tabler-outline/list-check, tabler-outline/device-desktop-analytics

## images
- p01_welcome: images/image_001_17.png | source=user | crop=no-crop
- p02_nav: images/image_002_13.png | source=user | crop=no-crop
- p03_dress: images/image_001_9.png | source=user | crop=no-crop
- p04_arc: images/image_003_8.png | source=user | crop=no-crop
- p04_roller: images/image_001_12.png | source=user | crop=no-crop
- p05_raceway: images/image_001_13.png | source=user | crop=no-crop
- p05_hole: images/image_002_9.png | source=user | crop=no-crop
- p06_process: images/image_001_8.png | source=user | crop=no-crop
- p07_ring: images/image_001_5.png | source=user | crop=no-crop
- p07_chamfer: images/image_004_3.png | source=user | crop=no-crop
- p08_segcomp: images/image_006_2.png | source=user | crop=no-crop
- p08_dryrun: images/image_007_2.png | source=user | crop=no-crop
- p09_stats: images/image_001_16.png | source=user | crop=no-crop
- p09_backup: images/image_001_11.png | source=user | crop=no-crop
- p10_config: images/image_001_15.png | source=user | crop=no-crop

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: breathing
- P05: dense
- P06: dense
- P07: dense
- P08: breathing
- P09: dense
- P10: anchor

## page_visualizations
- P06: table/metric_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
