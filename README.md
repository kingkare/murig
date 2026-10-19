# MuRig · 编程开发环境自动装配小工具

<p align="center">
  <img src="assets/murig.png" alt="MuRig 主界面" width="760"/>
</p>

<p align="center">
  一款基于 <b>Python + PySide6</b> 的跨平台桌面工具<br/>
  一键完成常用开发组件的 <b>下载 → 解压（编译）→ 环境变量配置</b>，让开发环境搭建不再是重复劳动
</p>

<p align="center">
  <img src="https://img.shields.io/badge/python-3.9+-blue.svg" alt="python"/>
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg" alt="platform"/>
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="license"/>
  <img src="https://img.shields.io/badge/GUI-PySide6-brightgreen.svg" alt="pyside6"/>
  <img src="https://gitee.com/super_rgh/murig/badge/star.svg?theme=dark" alt="Gitee Stars"/>
  <img src="https://gitee.com/super_rgh/murig/badge/fork.svg?theme=dark" alt="Gitee Forks"/>
</p>

<p align="center">
  <b>最新版本：v1.2.0</b> · 活跃维护中 ·
  <a href="https://github.com/vfaner/murig">GitHub</a> ·
  <a href="https://gitee.com/super_rgh/murig">Gitee</a> ·
  <a href="https://github.com/vfaner/murig/releases">Releases</a> ·
  <a href="https://github.com/vfaner/murig/issues">Issues</a>
</p>

| 🚀 **开箱即用** | 📦 **全流程自动化** |
|:---:|:---:|
| 内置 **29 个**常用组件，官方直链与版本实时抓取 | 下载 → 解压（编译）→ 环境变量，一次点击完成 |
| 📁 **安装位置可控** | 🖥️ **原生跨平台** |
| 全局 / 分类 / 单组件三级工作空间 | Windows、macOS（arm64 / x64）、Linux |

---

## 📖 目录

- [下载即用](#-下载即用推荐)
- [项目简介](#-项目简介)
- [功能特性](#-功能特性)
- [界面预览](#-界面预览)
- [快速开始](#-快速开始源码运行)
- [支持的组件](#-支持的组件)
- [使用说明](#-使用说明)
- [配置工作空间](#-配置工作空间安装目录)
- [项目结构](#-项目结构)
- [技术栈](#-技术栈)
- [常见问题](#-常见问题faq)
- [更新日志](#-更新日志)
- [参与贡献](#-参与贡献)
- [联系方式](#-联系方式)
- [支持作者](#-支持作者)
- [许可证](#-许可证)

---

## 📥 下载即用（推荐）

> **不需要 Python 环境，不需要克隆源码，双击即可运行。** 到 **[Releases 页面](https://github.com/vfaner/murig/releases/latest)** 下载对应系统的版本（[Gitee 镜像](https://gitee.com/super_rgh/murig/releases)同步发布）：

| 系统 | 下载文件 | 说明 |
|------|----------|------|
| 🪟 **Windows** | [`murig.exe`](https://github.com/vfaner/murig/releases/latest/download/murig.exe) | 双击运行，无需安装 |
| 🍎 **macOS (Apple Silicon)** | [`murig-macos-arm64.zip`](https://github.com/vfaner/murig/releases/latest/download/murig-macos-arm64.zip) | 解压后双击 `murig.app` |
| 🍎 **macOS (Intel 芯片)** | [`murig-macos-x64.zip`](https://github.com/vfaner/murig/releases/latest/download/murig-macos-x64.zip) | 解压后双击 `murig.app` |
| 🐧 **Linux (x64)** | [`murig-linux-x64`](https://github.com/vfaner/murig/releases/latest/download/murig-linux-x64) | `chmod +x` 后直接运行 |

首次启动提示：

- **macOS**：未做代码签名，若提示"无法验证开发者"，到「系统设置 → 隐私与安全性」点击 **"仍要打开"**，或执行 `xattr -cr murig.app`
- **Windows**：SmartScreen 弹"未识别应用"时，点击 **"更多信息 → 仍要运行"**

---

## 🧭 项目简介

MuRig 把「找官网、对系统和架构、下载解压、配置环境变量、开新终端验证」这套重复的体力活，收敛为桌面应用里的几次点击。

**适用场景**

- **新电脑 / 新入职**：半小时内拉起 Java、Python、前端、数据库、大数据、AI 等常用环境
- **教学与演示**：为机房、培训班批量准备统一版本的工具链
- **个人学习**：想试试某个中间件或数据库，又不想被安装步骤劝退

**它解决了什么**

- 官方下载源分散、命名规则各异 → 内置 29 个组件的官方直链与版本清单
- Windows / macOS / Linux 与 x64 / arm64 分发包不同 → 自动识别并选择正确的包
- 环境变量配置繁琐易错 → 自动写入并幂等更新，重复安装不产生脏数据
- 默认装 C 盘 / 家目录 → 全局、分类、单组件三级可配置安装目录

**项目定位**：开源、离线可用、只做「下载 + 解压 + 环境变量」三件事，不接管数据库初始化等系统级操作，边界清晰、可预期。

**安全与透明**：不收集任何用户数据；安装包全部来自组件官方源；环境变量只写入当前用户（Windows 用户级注册表 / macOS·Linux 的 shell 配置文件），以带标记的幂等块管理，可随时手动移除。

---

## ✨ 功能特性

- 🖥️ **跨平台**：Windows / macOS / Linux，自动识别 x64 / arm64 并挑选正确的官方分发包
- 📦 **一键装配**：内置 29 个组件（语言运行时、构建工具、关系型/信创数据库、大数据全家桶、AI CLI），下载 → 解压（编译）→ 环境变量配置全流程自动化
- 🗂️ **分类与搜索**：六大分类胶囊一键筛选；搜索框支持软件名 / 别名（`es`、`缓存`）/ 分类名（`数据库`）模糊匹配
- 🌐 **动态版本**：后台向各官方 API / 归档拉取最新版本列表，下拉框可键入过滤；抓取失败自动回退内置清单，离线可用
- 🔍 **智能检测**：依次检查 `XXX_HOME` → `PATH` → 常见安装路径，已配置的组件显示 ✓ 且不会重复写入
- 🛠️ **环境变量写入**：Windows 走 `winreg` 直写注册表（规避 `setx` 1024 字符限制）；macOS/Linux 向 shell 配置写入带 marker 的幂等块
- 📁 **可配置工作空间**：全局 / 分类 / 单组件三级安装目录，见 [配置工作空间](#-配置工作空间安装目录)
- 🎨 **现代化 UI**：无边框窗口、圆角卡片、渐变进度条、四色分级日志
- 🧠 **偏好记忆**：记住每个组件上次选择的版本，下次启动自动恢复

---

## 📸 界面预览

| 主界面 | 版本选择 |
|:---:|:---:|
| <img src="assets/murig.png" width="460"/><br/><sub>六大分类、模糊搜索、状态标签与实时日志</sub> | <img src="assets/murig_db_version.png" width="460"/><br/><sub>版本实时抓取官方源，键入关键字即可过滤</sub> |
| **工作空间设置** | **关于我们** |
| <img src="assets/murig_work.png" width="460"/><br/><sub>全局 / 分类 / 单组件三级安装目录</sub> | <img src="assets/murig_about.png" width="460"/><br/><sub>联系方式与产品导航</sub> |

---

## 🚀 快速开始（源码运行）

环境要求：Python **3.9+**；Windows 10/11、macOS 12+、Ubuntu 20.04+。

```bash
git clone https://github.com/vfaner/murig.git
cd murig
pip install -r requirements.txt   # PySide6 + requests
python main.py
```

- 首次启动自动创建工作目录（默认 `~/.env-tools/`，可在「工作空间」修改）
- macOS/Linux 装 Redis、Linux 装 PostgreSQL 需要 `make` 与 C 编译器；装 Claude Code 需先装 Node.js

工作目录布局：

```
~/.env-tools/              # 可在「工作空间」改到任意盘
├── jdk/
│   ├── downloads/         # 原始压缩包
│   └── jdk-17/            # 解压后的组件
├── maven/
└── ...
```

---

## 📦 支持的组件

> 表中为离线默认版本；启动后后台会自动向官方源抓取最新版本覆盖。大数据组件均依赖 JDK，请先安装 JDK。

### ☕ Java 相关

| 组件 | 环境变量 | 默认版本 |
|------|----------|----------|
| JDK (Temurin) | `JAVA_HOME` | 21 / 17 / 11 / 8 |
| Apache Maven | `MAVEN_HOME` | 3.9.x / 3.8.x |
| Apache Tomcat | `CATALINA_HOME` | 10.1 / 9.0 / 8.5 |

### 🐍 Python 相关

| 组件 | 环境变量 | 默认版本 | 说明 |
|------|----------|----------|------|
| Python | —（走 PATH） | 3.12 / 3.11 / 3.10 / 3.9 | |
| Miniconda | `CONDA_HOME` | py312 / py311 / py310 | 静默安装器模式 |

### 🎨 前端相关

| 组件 | 环境变量 | 默认版本 | 说明 |
|------|----------|----------|------|
| Node.js | `NODE_HOME` | 20 LTS / 18 LTS / 16 | 安装 Claude Code 的前置条件 |
| Git | — | MinGit (Windows) / 系统自带 | |

### 🗄️ 数据库

| 组件 | 环境变量 | 默认版本 | 说明 |
|------|----------|----------|------|
| MySQL Server | `MYSQL_HOME` | 9.7 / 8.4 LTS / 8.0 | 需自行 `mysqld --initialize`；可识别标准安装路径 |
| MariaDB | `MARIADB_HOME` | 12.3 / 11.4 LTS / 10.11 LTS | 需自行初始化数据目录 |
| SQL Server 2025 Express | — | 2025 Express | 仅 Windows，官方在线引导程序向导安装 |
| PostgreSQL | `PG_HOME` | 18 / 17 / 16 | Linux 源码自动编译；需自行 `initdb` |
| Redis | `REDIS_HOME` | 8.4 / 7.4 / 7.2 | macOS/Linux 源码自动 `make` |
| Elasticsearch | `ES_HOME` | 8.15 / 7.17 | 别名 `es` |
| openGauss | `OPENGAUSS_HOME` | 7.0 / 6.0 | 仅 Linux |
| 达梦 DM8 | — | 滚动最新 | zip 套 ISO，自动解出并提示挂载安装 |
| OceanBase | `OB_HOME` | 4.4 / 4.3 | 仅 Linux，纯 Python 解包 RPM |
| TiDB | `TIDB_HOME` | 8.5 / 8.1 / 7.5 | 仅 Linux |
| KingbaseES | `KINGBASE_HOME` | V9R3C11 / V8R6C8 | 仅 Linux，便携 server 包自带 license |
| YashanDB | `YASHANDB_HOME` | 23.4.1 | 仅 Linux，`yasboot` 初始化 |

### 📊 大数据

| 组件 | 环境变量 | 默认版本 |
|------|----------|----------|
| Apache Hadoop | `HADOOP_HOME` | 3.5 / 3.4 / 3.3 |
| Apache ZooKeeper | `ZOOKEEPER_HOME` | 3.9 / 3.8 |
| Apache Hive | `HIVE_HOME` | 4.2 / 4.0 / 3.1 |
| Apache HBase | `HBASE_HOME` | 3.0 / 2.6 |
| Apache Spark | `SPARK_HOME` | 4.2 / 4.0 / 3.5 |
| Apache Flink | `FLINK_HOME` | 2.3 / 1.20 / 1.18 |
| Apache Kafka | `KAFKA_HOME` | 4.3 / 3.9 / 3.8 |

### 🤖 AI 相关

| 组件 | 环境变量 | 默认版本 | 说明 |
|------|----------|----------|------|
| Ollama | —（走 PATH） | 0.12 / 0.3 | 本地大模型运行工具 |
| Claude Code | `CLAUDE_CODE_HOME` | 跟随 npm 最新 | npm 便携安装（需先装 Node.js） |
| CC-Switch | — | 4.0.x | Claude 供应商切换；Win 便携版 / .app / AppImage |

> ℹ️ 官网无免登录直链、暂未收录的数据库：IBM DB2、瀚高 HighGo、海量 Vastbase、南大通用 GBase、神通 Oscar，需要时请自行到官网申请。

---

## 📝 使用说明

1. **筛选（可选）**：点击分类胶囊，或在搜索框输入软件名 / 别名 / 分类名
2. **选择版本**：下拉框点选，或键入关键字（`21`、`3.12`、`LTS`）实时过滤
3. **下载并安装**：流式下载（可取消）→ 解压（源码包自动编译）→ 写入 `XXX_HOME` 并把 `bin` 追加到 `PATH`
4. **配置环境变量**：本地已下载的组件只执行环境变量配置
5. **查看日志**：底部日志区四色分级显示每一步执行情况

环境变量生效：Windows 新开终端即可；macOS/Linux 执行 `source ~/.zshrc`（或重开终端）。验证：`java -version`、`mvn -v`、`python --version`、`node -v`、`mysql --version`。

---

## 🔧 配置工作空间（安装目录）

组件默认装到内置目录 `~/.env-tools/`（Windows 下即 C 盘）。点击标题栏 **「工作空间」** 按钮打开设置弹窗，安装位置解析优先级：

1. **组件自定义**：组件卡片上的文件夹图标按钮单独指定（右键该按钮可清除）；
2. **分类工作空间**：为六大分类分别指定目录；
3. **全局默认**：一键修改所有组件的安装位置；
4. 均未设置时回退内置默认 `~/.env-tools/`。

说明：

- 设置保存在 `~/.murig/config.json`，旧版 `~/.env-tools/config.json` 首次启动自动迁移；
- **已安装的组件原地不动**，环境变量仍指向旧路径，检测与使用不受影响；
- 下载缓存跟随当前工作空间，更换后未下载的组件需重新下载；
- 每张卡片的「安装到：…」实时显示该组件实际会安装到的目录。

---

## 📁 项目结构

```
murig/
├── main.py                             # 主程序：UI + 下载 / 解压 / 环境变量逻辑
├── requirements.txt                    # PySide6 + requests
├── murig.spec                          # PyInstaller 打包配置
├── README.md / README_EN.md            # 中文 / 英文说明
├── LICENSE                             # MIT
├── .github/workflows/
│   └── build-and-release.yml           # 四平台构建与自动发布
└── assets/                             # 截图与打赏二维码
```

---

## 🏗️ 技术栈

- **语言 / GUI**：Python 3.9+、PySide6（Qt 6 官方 Python 绑定）
- **网络**：`requests`，流式下载 + 官方源版本抓取，失败自动降级
- **解包**：`zipfile` / `tarfile`，OceanBase RPM 由内置 xz + cpio 解析器解包
- **环境变量**：Windows 通过 `winreg` 直写注册表；macOS/Linux 向 shell rc 写入带 marker 的幂等块
- **并发**：`QThread` 后台下载与版本抓取，UI 全程不阻塞
- **架构**：单文件应用（`main.py`），无数据库、无服务端依赖
- **构建发布**：PyInstaller + GitHub Actions，一次 tag 产出 Windows / macOS (arm64 + x64) / Linux 四份产物

---

## ❓ 常见问题（FAQ）

**版本抓取失败 / 下载卡住？** 抓取失败自动回退内置版本列表，功能不受影响；下载卡住点「取消」重试，或更换下载镜像。

**环境变量写入失败 / 会覆盖旧值吗？** Windows 默认写用户级变量，通常无需管理员权限，失败时以管理员身份重跑。重复安装会用最新路径覆盖 `XXX_HOME`，`PATH` 只追加不重复。

**MySQL 解压后能直接用吗？** 不能，还需自行 `mysqld --initialize`；本工具只负责下载 + 解压 + 环境变量。

**支持哪些归档格式？** `.zip`、`.tar.gz`、`.tar.xz`（MySQL Linux）、魔术字节识别的 `.tar`（KingbaseES 实为 gzip）、RPM（OceanBase，纯 Python 解包）、AppImage（需系统支持 FUSE）。

**安装 Claude Code 提示找不到 npm？** 先到「前端相关」分类安装 Node.js，再回到 Claude Code 卡片点击安装。

**信创数据库支持到什么程度？** openGauss / OceanBase / TiDB / KingbaseES / YashanDB 仅 Linux，自动下载并解包到工作目录；建用户、建数据目录等实例初始化按日志提示参照官方文档完成。

**如何彻底移除本工具写入的环境变量？** macOS/Linux 删除 shell 配置中 `# >>> env-auto-setup:<组件> >>>` 与 `# <<< env-auto-setup:<组件> <<<` 之间的块（PATH 条目同理）；Windows 到「系统属性 → 环境变量 → 用户变量」删除对应项即可。

---

## 🗺️ 更新日志

- **v1.2.0**（2026-10-10）：新增三级可配置工作空间（全局 / 分类 / 单组件安装目录）、工作空间扫描检测、卡片「安装到：…」提示、全新文件夹图标与界面细节优化
- **v1.1.0**（2026-10-08）：品牌升级为 MuRig，macOS 提供 arm64 / x64 双架构安装包，README 与项目署名规范化
- **v1.0.x**：首个稳定版本，内置 29 个常用开发组件，支持下载、解压（编译）与环境变量自动配置

完整版本历史与安装包见 [Releases](https://github.com/vfaner/murig/releases)。

---

## 🤝 参与贡献

欢迎提交 Issue 与 Pull Request，尤其欢迎补充新的组件、国内镜像与文档改进。

1. Fork 本仓库并创建分支：`git checkout -b feat/your-feature`
2. 提交改动（建议一个提交只做一件事）：`git commit -m "feat: ..."`
3. 推送分支并创建 Pull Request，说明动机与验证方式
4. 发现 Bug 或有新组件需求，直接提 [Issue](https://github.com/vfaner/murig/issues) 即可

**开发提示**

- 新增组件：在 `main.py` 的 `build_components()` 中补充 `Component` 定义，下载地址请使用官方或镜像直链
- 提交前请确认 `python main.py` 可正常启动；涉及下载逻辑的改动请实际跑通一次
- 环境变量相关改动请同时考虑 Windows / macOS / Linux 三个平台

---

## 📮 联系方式

- 问题反馈：[GitHub Issues](https://github.com/vfaner/murig/issues) · [Gitee Issues](https://gitee.com/super_rgh/murig/issues)
- QQ：817094 / 2912167928
- QQ 群：426669837
- 微信：qqmu66
- 产品导航：<https://nav.qqmu.com>

---

## 💖 支持作者

如果这个小工具对你有帮助，欢迎请作者喝杯咖啡 ☕：

<table>
  <tr>
    <td align="center">
      <img src="assets/wechat.png" alt="微信" width="200"/><br/>
      <b>微信</b>
    </td>
    <td align="center">
      <img src="assets/alipay.png" alt="支付宝" width="200"/><br/>
      <b>支付宝</b>
    </td>
    <td align="center">
      <img src="assets/qq.png" alt="QQ" width="200"/><br/>
      <b>QQ</b>
    </td>
  </tr>
</table>

也欢迎 ⭐ Star、🐛 提 Issue、🔀 提 PR。

---

## 📄 许可证

本项目基于 **MIT License** 开源，版权所有 © 2026 [**沐编程**](https://nav.qqmu.com)。完整条款见 [LICENSE](LICENSE)。

---

<p align="center">
  Made with ❤️ by <b><a href="https://nav.qqmu.com">沐编程</a></b><br/>
  <sub>如果觉得有用，别忘了给个 ⭐ Star！</sub>
</p>
