# AutoFusion Personal

AutoFusion Personal 是一款面向 Windows 的本地工具管理程序，为已适配的第三方软件提供统一的下载、安装、启动与管理入口。

软件遵循第三方项目原有的安装与卸载方式，并提供模块状态管理、离线安装包库、软件目录诊断及运行日志等功能，让日常工具管理更加集中、直观。

AutoFusion Personal 完全免费，无需注册账号。当前支持范围以程序内已适配的模块为准，未来将持续完善功能和扩展兼容范围。

> 本仓库只发布 Windows 发行包与说明文档。AutoFusion App/Core 闭源，不公开源码、构建脚本、测试代码或用户数据。

## 主要功能

- **模块状态管理**：集中查看已适配模块的状态，并按各模块的适配方式提供对应操作。
- **遵循原版安装方式**：使用官方安装器的项目仍走原版安装与卸载流程；便携包项目按受管文件清单管理。
- **离线安装包库**：保存、校验并管理本地安装包副本，不会自动安装或运行导入的文件。
- **软件目录诊断（只读）**：查看常见安装目录与候选位置，不修改第三方文件。
- **任务队列与运行日志**：任务队列默认模拟运行，配合日志排查操作与错误。
- **支持开发者**：捐赠完全自愿，不解锁任何功能。

部分下载与安装操作需要访问第三方官方来源；网络可用性与第三方软件本身由相应项目负责。

## 系统要求

- Windows 10 / 11，x64
- 目录版 ZIP，解压后直接运行，无需另装 Python
- 用户配置写入 `%LOCALAPPDATA%\AutoFusionPersonal`

## 下载与校验

从 [Releases](https://github.com/kizyyyture-dev/AutoFusion-Personal/releases) 下载最新版本的两个附件：

| 文件 | 说明 |
| --- | --- |
| `AutoFusionPersonal_1.0.0_Windows_x64.zip` | Windows x64 发行包 |
| `AutoFusionPersonal_1.0.0_Windows_x64.zip.sha256.txt` | 对应的 SHA-256 校验值 |

在 ZIP 所在目录打开 PowerShell：

```powershell
(Get-FileHash .\AutoFusionPersonal_1.0.0_Windows_x64.zip -Algorithm SHA256).Hash.ToLower()
```

v1.0.0 的发布值为：

```text
e4da07ba9c92487cf8da15409c06961b225449f6d115c29af4dd301a62b250a9
```

输出应与校验文件中的值一致。SHA-256 只能核对文件与发布值是否相同，不能代替发布者身份验证。

解压**整个** ZIP，进入 `AutoFusionPersonal` 文件夹运行 `AutoFusionPersonal.exe`，并保留 `_internal` 目录。

## 安全状态（v1.0.0）

- 火绒安全软件 6.0.12.3（病毒库 2026-10-29）已对发行包解压目录与最终 ZIP 分别扫描，结果为**未发现风险**；扫描记录随包提供（`安全扫描状态.txt`）。
- **Windows Defender 扫描未成功完成**：构建机上的扫描命令报错，本版本没有 Defender 结论。
- 程序**未进行 Authenticode 数字签名**，首次运行可能触发 SmartScreen 提醒。
- 请勿为运行本软件而关闭杀毒软件、防火墙或 SmartScreen，也不要添加白名单。
- 闭源打包只能提高逆向成本，不能保证程序无法被逆向或重新封装；捐赠前请核对收款人。

## 使用限制

- 仅管理程序内已适配的模块，不支持任意软件或任意安装包的自动安装。
- 不提供全自动任务执行；任务队列默认模拟运行。
- 独立版不执行源码替换式自动升级，更新需从本仓库 Releases 手动下载并校验。
- 150% 显示缩放且窗口较窄时，「设置」页部分按钮文字可能被裁切，功能不受影响。

## 反馈

请通过 [Issues](https://github.com/kizyyyture-dev/AutoFusion-Personal/issues) 反馈问题，并附上 Windows 版本、程序版本与复现步骤。分享日志前请删除账号、路径等隐私信息。

## 许可与第三方归属

- AutoFusion 自身的使用条款见 [LICENSE.txt](LICENSE.txt)，该条款不改变第三方组件的许可。
- 随包运行时（Python、Tcl/Tk、OpenSSL、zlib、libffi、PyInstaller、MSVC/UCRT 等）的版本、来源与许可原文见 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) 及发行包内 `licenses` 目录。
- 本程序**不捆绑** OK-WW（ok-wuthering-waves）、StarRailAssistant、7-Zip 的程序本体；这些项目由用户通过各自作者的官方渠道获取，其版权与许可归各自作者所有。
