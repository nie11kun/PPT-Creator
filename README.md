# PPT-Creator

基于 [PPT Master](https://github.com/hugohe3/ppt-master)（`v6.10.0`）构建的本地 AI 原生可编辑演示文稿创作工作区。支持从 HTML 手册、PDF、Word（`.docx`）、Excel（`.xlsx`/`.xlsm`）、PowerPoint（`.pptx`）、网页 URL 或纯主题描述出发，生成带有真实可编辑 DrawingML 形状、原生表格/图表与演讲者备注的 `.pptx` 文件。

---

## 目录

- [环境要求与技能配置](#环境要求与技能配置)
- [目录结构说明](#目录结构说明)
- [标准创作与可视化微调流程](#标准创作与可视化微调流程)
- [常用命令速查](#常用命令速查)
- [已有项目清单](#已有项目清单)
- [Git 版本管理与 Windows 注意事项](#git-版本管理与-windows-注意事项)

---

## 环境要求与技能配置

- **Python 版本**：Python 3.10–3.14（本机已安装 Python 3.14.2，Windows 环境请统一使用 `python`，避免命中 WindowsApps 的 `python3` 占位符）
- **技能安装路径**：全局安装于 `C:\Users\Marco Nie\.gemini\config\skills\ppt-master`（Antigravity 自动发现并加载）
- **依赖安装**：

```powershell
$SKILL_DIR = "$env:USERPROFILE\.gemini\config\skills\ppt-master"
python -m pip install -r "$SKILL_DIR\requirements.txt"
```

> 核心依赖已全部就绪，涵盖 `python-pptx`、`XlsxWriter`、`skia-pathops`、`uharfbuzz`、`edge-tts`、`PyMuPDF`、`mammoth`、`markdownify`、`ebooklib`、`nbconvert`、`openpyxl`、`Pillow`、`numpy`、`requests`、`beautifulsoup4`、`curl_cffi`、`google-genai`、`flask`、`PyYAML`。

- **可选扩展配置（`.env`）**：
  - 如需启用脚本内置 AI 生图（`image_gen.py`）、商业图库搜索（`image_search.py`）或云端 TTS 旁白，可参考全局技能目录下的 `.env.example` 在本工作区根目录或技能目录新建 `.env`。
  - `.env` 与 `.env.*` 已被 `.gitignore` 自动忽略，不会误提交密钥。

---

## 目录结构说明

### 工作区根目录

```text
PPT-Creator/
├── .gitignore      # Git 忽略规则（排除缓存、日志、锁文件及临时预览产物）
├── README.md       # 工作区说明文档
└── projects/       # 各个独立 PPT 创作项目目录
```

### 单个项目目录结构（`projects/<project_name>/`）

| 路径 | 职责说明 | Git 追踪策略 |
|---|---|---|
| `design_spec.md` | 完整的 I–X 章节设计规范与逐页内容大纲 | 保留追踪 |
| `spec_lock.md` | 跨页锚点与执行锁定配置（画布、色板、字体、图标、节奏等） | 保留追踪 |
| `sources/` | 归档的原始输入材料、转换后的 Markdown 及伴生 `*_files/` | 保留追踪 |
| `images/` | 项目运行时图片池与 `image_manifest.json` | 保留追踪 |
| `icons/` | 通过 `icon_sync.py` 同步的项目本地 SVG 图标库 | 保留追踪 |
| `templates/` | 项目级模板规格与原型文件（如启用模板路线） | 保留追踪 |
| `svg_output/` | 手写生成的每页原生 SVG 源码（**导出唯一权威源**） | 保留追踪 |
| `notes/` | `total.md` 全稿及按页拆分的演讲者备注 `.md` | 保留追踪 |
| `exports/` | 最终导出的原生 DrawingML `.pptx` 成品 | 默认保留（可在 `.gitignore` 取消注释以忽略） |
| `analysis/` | `image_analysis.csv` 及 PPTX 结构分析中间产物 | 保留追踪 |
| `confirm_ui/` | 两阶段确认推荐 JSON 与用户提交回执（`server.log` 已忽略） | 忽略日志 |
| `validation/` | SVG 质检 JSON 报告与导出后检报告（`workflow.log` 已忽略） | 忽略日志 |
| `svg_final/` | 内嵌图片/图标后的自包含 SVG 预览（仅作预览，不作导出源） | 已忽略 |
| `live_preview/` | 浏览器实时预览运行时锁、编辑与标注历史 | 已忽略 |
| `backup/` | 每次导出前自动备份的历史 `svg_output/` 快照 | 已忽略 |

---

## 标准创作与可视化微调流程

1. **提出需求**：在对话中提供源文档路径（如 PDF/HTML/DOCX/XLSX/PPTX）、网址或主题及页数要求。
2. **源材料转换与建项**：自动将材料转为标准 Markdown 并初始化 `projects/<name>_<YYYYMMDD>` 项目。
3. **两阶段交互确认（Confirm UI，默认 `http://127.0.0.1:5050`）**：
   - **第一阶段**：确认受众、沟通意图、核心信息、画布比例及自由设计/模板模式；
   - **第二阶段**：在 3 套差异化整套设计方向中选择配色、字体、图标风格、图片策略及备注/动画/旁白开关。
4. **规范锁定与逐页创作**：生成 `design_spec.md` 与 `spec_lock.md` 并校验通过后，逐页编写 `svg_output/*.svg`（前 5 页后过早期质检，全稿完成后过终检），并生成 `notes/total.md`。
5. **实时预览与可视化编辑（Live Preview，默认 `http://127.0.0.1:6060`）**：
   - 支持实时查看每页渲染效果；
   - 支持直接拖拽微调位置、修改文字/字号/颜色并点击 **Apply changes** 写回 `svg_output/`；
   - 支持为元素添加编辑标注（**Add annotation**），随后在对话中回复“应用标注”即可让 AI 定向改写并重新导出。
6. **序列化导出**：依次完成备注拆分、自包含预览生成与原生 `.pptx` 导出及 Postflight 后检。

---

## 常用命令速查

在 PowerShell 中先设置技能目录变量：

```powershell
$SKILL_DIR = "$env:USERPROFILE\.gemini\config\skills\ppt-master"
```

```powershell
# 1. 运行技能完整性检查（每次执行工作流前置校验）
python "$SKILL_DIR\scripts\attribution_guard.py"

# 2. 将源文档（HTML/PDF/DOCX/XLSX/PPTX/URL）转换为 Markdown
python "$SKILL_DIR\scripts\source_to_md.py" <source_path> -o <output_dir>

# 3. 初始化项目并导入源材料
python "$SKILL_DIR\scripts\project_manager.py" init <project_name>
python "$SKILL_DIR\scripts\project_manager.py" import-sources <project_path> <sources_or_dir>

# 4. 校验 design_spec.md 与 spec_lock.md
python "$SKILL_DIR\scripts\project_manager.py" validate <project_path>

# 5. 启动实时预览与可视化编辑器（默认端口 6060）
python "$SKILL_DIR\scripts\svg_editor\server.py" <project_path> --live

# 6. 运行 SVG 全页质量终检
python "$SKILL_DIR\scripts\svg_quality_checker.py" <project_path> --canonical-authoring --stage final --json

# 7. 串联导出流程（拆分备注 → 自包含预览 → 原生 PPTX）
python "$SKILL_DIR\scripts\total_md_split.py" <project_path>
python "$SKILL_DIR\scripts\finalize_svg.py" <project_path>
python "$SKILL_DIR\scripts\svg_to_pptx.py" <project_path>
```

> 若页面包含已标定 `data-pptx-replace-with="table"` / `"chart"` 的原生数据对象并希望导出为 PowerPoint 原生表格/图表对象，可在 `svg_to_pptx.py` 后追加 `--native-charts-and-tables`。

---

## 已有项目清单

### `projects/sinumerik_internal_thread_grinder_20261123`

- **主题**：`TEST` 数控内螺纹磨床 HMI 3.29.0 系统介绍（10 页，16:9 宽屏，工业精密青 · `soft-rounded` 风格）
- **源材料**：基于 SINUMERIK 内螺纹磨床 HTML 用户手册（18 份有效章节页面及 57 张原生 800×600 HMI 实机截图）
- **内容覆盖**：封面与全流程链路 → 双层界面导航与面板优先级 → 砂轮修整与标定 → 多齿型与滚轮配置 → 手动与六大自动对刀 → 四级工艺磨削表与测后补偿 → 8 项磨削扩展功能（上下篇）→ 加工统计/寿命预警/参数备份 → 四级权限安全体系与落地建议
- **验证状态**：`svg_quality_checker.py --canonical-authoring --stage final` **10/10 全部通过**（0 错误、0 警告）；`svg_to_pptx.py` Postflight `status=passed`、`slides=10`、`warning_categories=0`
- **交付成品**：[`projects/sinumerik_internal_thread_grinder_20261123/exports/sinumerik_internal_thread_grinder_20261123_121205.pptx`](projects/sinumerik_internal_thread_grinder_20261123/exports/sinumerik_internal_thread_grinder_20261123_121205.pptx)

---

## Git 版本管理与 Windows 注意事项

- **Git 提交边界**：`.gitignore` 已屏蔽 `live_preview/`、`backup/`、`svg_final/`、`*.lock`、`*.log` 与 `.env`；如需仅用 Git 管理文本规范与 SVG 源码而不提交二进制 `.pptx`，可取消 `.gitignore` 中 `# projects/*/exports/*.pptx` 的注释。
- **Windows 命令差异**：Windows 应用商店默认自带退出码为 `9009` 的 `python3` 占位符，请始终使用 `python` 执行所有脚本。
- **导出权威源边界**：`svg_output/` 是唯一受支持的可编辑 PPTX 导出输入源；`svg_final/` 仅用于浏览器或静态 SVG 预览，切勿依赖 PowerPoint 手动“转换为形状”。
