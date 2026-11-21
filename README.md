# LaserBoard — 实时激光写字板与多区联动系统

**[中文](#中文说明) | [English](#english)**

---

## 中文说明

**LaserBoard** 是一款面向演艺现场、婚礼互动与创意装置的 **实时多点触控激光写字板 + 多区联动工作站**（Windows x64 桌面引擎 + 移动端 TUIO / NDI 控制端）。移动端通过 NDI 实时接收高帧率画板画面并回传多点触控（TUIO UDP），桌面端经振镜点流优化后直接推送给 **Pangolin BEYOND**，支持 1~9 路独立画布与无缝走马灯接力滚动。

### 核心特性

| 模块 | 说明 |
| --- | --- |
| **低延迟触控绘制** | 移动端 NDI `"DRAW"` 实时画板回传 + TUIO UDP (`:3333`) 多点触控路由，支持本地预览窗直接书写与调试 |
| **多区激光输出** | 支持 1~9 路独立画布（`Zone 1..9`）映射至 **Pangolin BEYOND**；支持单区聚焦、九宫格总览与自定义排序列数 |
| **无缝走马灯滚动** | 开启滚动模式后，多路画布按排列顺序自动拼接并向左侧/右侧无缝循环接力滚动，速度与方向可实时调节 |
| **色彩合成与拾色器** | 内置 5 种色彩模式（纯色 / 彩虹 / 水平彩虹 / 圆形彩虹 / 放射彩虹），支持色相滑块、预设色板与色彩动画相位速度 |
| **待机展示与书写切换** | 支持一键保存当前画面为待机快照；**手握笔**图标为书写模式、**眼睛**图标为展示待机模式；支持闲置自动进入待机，点击画板立即唤醒书写 |
| **振镜安全优化** | 复刻激光振镜采样步长、拐角驻留与消隐跳线插值算法，支持矢量模式、自适应降频保护与 60 FPS 稳定输出 |
| **无头与低负载模式** | 窗口最小化或 `--headless` 纯后台运行时自动跳过冗余 UI 像素渲染，保持激光与 NDI/TUIO 零丢帧稳定输出 |
| **双语界面与权限自检** | 顶部一键切换 **中文 / EN**；自动检测 Windows UAC/UIPI 权限不匹配并支持一键以管理员身份重启以连接 BEYOND |

### 下载与运行

1. **Windows 桌面端**：在 [Releases](https://github.com/RayInst/LaserBoard/releases) 页面下载最新的 `LaserBoard_Win64.zip` 并解压到任意目录（路径尽量避免特殊字符）；如需激光硬件输出，先启动 **Pangolin BEYOND**，再运行 `LaserBoard.exe`。
2. **移动端控制端**（与电脑处于同一局域网）：
   - **Android（安卓端）**：直接在 [Releases](https://github.com/RayInst/LaserBoard/releases) 页面下载配套的 `laserboard.apk` 安装使用。
   - **iOS / iPadOS（苹果端）**：请在 **App Store** 商店搜索下载 **Tmote**。
3. 在移动端连接 NDI 视频源 `DRAW`（并将 TUIO 发送至电脑 IP 与默认端口 `3333`）即可开始实时激光书写；也可直接在桌面端点击「画板窗」进行本地绘制测试。

桌面压缩包已内置 `BEYONDIO.dll` 与 `Processing.NDI.Lib.x64.dll`，免安装、零配置，运行状态与待机画面自动保存。

### 授权与试用

- **未激活试用**：每次启动提供 **30 分钟全功能试用**，期间激光输出与 NDI 画板每隔 10 秒会叠加 2 秒矢量 `DEMO` 水印；30 分钟到期后自动关闭输出并通知移动端（重启软件可开启新一轮试用）。
- **激活商业授权**：点击顶部试用状态徽章或展开「商业授权」面板，输入 `LBD-` 授权码联网激活，或导入离线 `license.dat`；授权绑定本机硬件特征码，支持联网解绑换机。
- **购买授权**：访问 **[r1gy.com/product/laserboard](https://r1gy.com/product/laserboard)**。

### 版本更新

软件启动时会匿名检查本仓库 [Releases](https://github.com/RayInst/LaserBoard/releases) 页面是否有新版本，发现新版本时顶部会出现更新提示；也可点击顶部 `v版本号` 徽章随时手动检查更新与查看发布说明。

### 系统要求

- Windows 10 / 11 64 位
- 激光输出需安装 **Pangolin BEYOND**
- 支持 OpenGL / wgpu 的现代显卡驱动

---

## English

**LaserBoard** is a real-time **multi-touch laser writing board and multi-zone show controller** for live events, weddings, and interactive installations (Windows x64 desktop engine + mobile TUIO / NDI controller). Mobile devices receive the live canvas via NDI and send multi-touch strokes over TUIO UDP, while the desktop engine optimizes galvo point streams and pushes them straight to **Pangolin BEYOND** across 1–9 independent zones with seamless marquee scrolling.

### Key Features

| Module | Description |
| --- | --- |
| **Low-Latency Touch Drawing** | Live NDI `"DRAW"` video stream to mobile + TUIO UDP (`:3333`) multi-touch routing; also supports drawing directly inside the desktop canvas window |
| **Multi-Zone Laser Output** | 1–9 independent canvases (`Zone 1–9`) mapped to **Pangolin BEYOND**; single-zone focus, multi-zone grid preview, and configurable column layout |
| **Seamless Marquee Scroll** | Automatically stitches active zones in order and scrolls continuously across all zones with real-time speed and direction control |
| **Color Synthesis & Palette** | 5 built-in color modes (Solid / Rainbow / Horizontal / Circular / Radial), hue spectrum slider, quick swatches, and animated color speed |
| **Standby & Writing Modes** | Save any artwork as a persistent standby snapshot; distinct **Hand-Pen** (writing) and **Eye** (showcase/standby) icons; auto-standby on idle with instant wake-on-touch |
| **Galvo Stream Optimization** | Step-size resampling, corner dwell, and blanked jump interpolation with adaptive point-budget protection and rock-solid 60 FPS output |
| **Headless & Zero-Redundancy** | Automatically skips redundant UI pixel rendering when minimized or running with `--headless`, keeping laser, TUIO, and NDI pipelines jitter-free |
| **Bilingual UI & UAC Check** | Switch **中文 / EN** anytime in the top bar; detects Windows UAC/UIPI elevation mismatch against `BEYOND.exe` with one-click Administrator restart |

### Download & Run

1. **Windows Desktop**: Download the latest `LaserBoard_Win64.zip` from the [Releases](https://github.com/RayInst/LaserBoard/releases) page and extract it anywhere. For laser hardware output, launch **Pangolin BEYOND** first, then run `LaserBoard.exe`.
2. **Mobile Controller** (on the same LAN as the desktop):
   - **Android**: Download `laserboard.apk` directly from the [Releases](https://github.com/RayInst/LaserBoard/releases) page and install it.
   - **iOS / iPadOS**: Search for and download **Tmote** from the **App Store**.
3. Connect the mobile app to the NDI source `DRAW` (and send TUIO to the desktop IP on default port `3333`) to start drawing live, or click **Canvas** in the desktop top bar to draw locally.

The desktop release archive already bundles `BEYONDIO.dll` and `Processing.NDI.Lib.x64.dll` — portable and ready out of the box.

### Licensing & Trial

- **Unlicensed Trial**: Each launch grants a **30-minute full-feature trial**, overlaying a 2-second vector `DEMO` watermark every 10 seconds on laser and NDI outputs. Outputs stop cleanly on expiry (restart the app to begin another trial session).
- **Commercial Activation**: Click the top-bar trial badge or open the License section to paste an `LBD-` online activation code or import an offline `license.dat`. Licenses are hardware-bound and can be deactivated online to transfer machines.
- **Purchase License**: Visit **[r1gy.com/product/laserboard](https://r1gy.com/product/laserboard)**.

### Updates

On startup LaserBoard anonymously checks this repository's [Releases](https://github.com/RayInst/LaserBoard/releases) page for newer versions and surfaces an update badge in the top bar. You can also click the `v<version>` badge anytime to check manually.

### System Requirements

- Windows 10 / 11 x64
- **Pangolin BEYOND** installed for laser output
- Modern GPU driver supporting OpenGL / wgpu
