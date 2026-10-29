# AutoFusion Personal V1.0.0（Windows x64）

AutoFusion Personal 是一个 Windows 桌面小工具，用一个界面集中管理已经安装或计划安装的第三方工具（鸣潮助手 OK-WW、崩坏：星穹铁道助手 StarRailAssistant、7-Zip 等），并提供本机离线安装包库、目录诊断、任务队列与运行日志。

**本仓库只发布编译好的 Windows 程序与说明文档。项目闭源，不包含 App/Core 源码、构建脚本、测试代码或任何用户数据。**

## 下载与安装

1. 打开本仓库的 **Releases** 页面，下载最新版本的
   `AutoFusionPersonal_1.0.0_Windows_x64.zip` 与同名的 `.sha256.txt` 校验文件。
2. 核对 SHA-256（Windows 11 可直接在 PowerShell 里执行）：

   ```powershell
   Get-FileHash .\AutoFusionPersonal_1.0.0_Windows_x64.zip -Algorithm SHA256
   ```

   结果应与 `.sha256.txt` 中的哈希完全一致。
3. **解压整个 ZIP**，进入 `AutoFusionPersonal` 文件夹，双击 `AutoFusionPersonal.exe`。
   - 不要只把 EXE 拖出来单独运行，`_internal` 是运行必需的依赖目录。
   - 不需要另外安装 Python。
4. 首次运行可能出现 Windows SmartScreen 提醒（本程序尚未做 Authenticode 代码签名）。
   **请勿为了运行本软件而关闭 Defender、火绒、SmartScreen 或添加白名单。**

程序不会写入系统目录，用户配置保存在 `%LOCALAPPDATA%\AutoFusionPersonal`，模块安装目录默认为 `D:\AutoFusion\fusion`（可在"设置"里更改）。解压包本身不含 `fusion`、`OfflinePackages` 或用户配置。

## 功能

- **操作台**：已收录模块概览、在线搜索 GitHub、快捷执行队列（默认模拟运行，不直接动别人的程序）。
- **模块管理**：统一查看、安装、打开原版界面与卸载；安装/卸载交给原版安装程序或受管清单。
- **设置**：模块目录、安装包保留策略、单模块超时、目录诊断。
- **运行日志**：安装、下载、操作与卸载记录。
- **支持开发者**：完全自愿的捐赠入口，不解锁任何额外功能。

## 安全与隐私

- 无云账户、无服务器遥测、无后台收费 API；不调用任何付费服务。
- 本版本已用本机火绒安全软件 6.0.12.3（病毒库 2026-10-29 19:42）对解压目录与最终 ZIP 本体完整扫描，结果为**未发现风险**。扫描记录随 ZIP 一起分发（`安全扫描状态.txt`、`.安全扫描记录.txt`）。
- **Windows Defender 的扫描命令在构建机上执行失败**（"Errors were encountered when attempted to scan your device."），因此本包**没有** Defender 的扫描结论，请自行用你信任的安全软件复核。
- 程序未做数字签名；哈希与扫描结果都不能证明发布者身份，只能证明文件未被改动。
- 第三方工具的下载与安装来自各自作者（GitHub / SourceForge 等），AutoFusion 不保证每条线路可用，也不替代你对第三方软件的判断。
- 独立版不执行旧的"源码替换式"自动升级；更新请通过本仓库 Releases 人工核验。

## 第三方组件与许可

发行包内 `licenses\` 目录附带了随包运行时的许可原文：

| 组件 | 版本 | 许可 |
| --- | --- | --- |
| Python | 3.13.12 | PSF License 2.0 |
| Tcl / Tk | 8.6 | Tcl/Tk License（BSD 式） |
| OpenSSL | 3.0.18 | Apache License 2.0 |
| zlib | 1.3.1 | zlib License |
| libffi | 3.4.6 | MIT License |
| PyInstaller | 6.22.3 | GPL-2.0-or-later + Bootloader 例外 |
| MSVC / UCRT 运行时 | — | Microsoft 可再发行组件条款 |

完整清单、原文文件与来源链接见 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) 与包内 `licenses\README-许可说明.txt`。

## 许可

本程序为闭源软件，版权归作者所有。允许免费下载与使用官方原版发行包；禁止反编译、修改后再分发、单独提取内置图片或收款码、以及任何形式的商业转售。详见 [LICENSE.txt](LICENSE.txt)。

## 反馈

请通过本仓库的 Issues 反馈问题，附上 Windows 版本、程序版本与"运行日志"页里的相关记录。**不要**在 Issue 里贴出你的付款码、账号或其他隐私信息。
