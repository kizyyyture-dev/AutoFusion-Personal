# AutoFusion Personal — Windows 本地工具统一管理平台

AutoFusion Personal 是一款面向 Windows 的本地工具管理程序，旨在为已适配的第三方软件提供统一的下载、安装、启动与管理入口。

它尊重第三方项目原有的安装方式，并提供模块状态管理、离线安装包库、软件目录诊断与运行日志等功能，让常用工具的管理更加集中、直观。

软件完全免费，无需注册账号。当前支持范围以程序内已适配的模块为准，更多功能与适配项目将在后续版本中逐步完善。

**本仓库仅公开 Windows 发行包与说明文档。AutoFusion App/Core 闭源，不公开源码、构建脚本、测试代码或用户数据。**

## 核心功能

- **已适配模块管理**：集中查看模块状态，并提供对应适配方式支持的下载、安装、启动和管理操作。具体可用操作因模块而异。
- **遵循原版安装方式**：使用官方安装器的项目继续通过原版安装与卸载流程；便携包项目可按受管文件清单管理。
- **离线安装包库**：保存、校验和管理本地安装包副本；导入文件不会自动安装或运行任意程序。
- **本机目录诊断**：只读查看部分软件的常见目录及候选位置，不清理或改动第三方文件。
- **任务队列与运行日志**：任务队列默认模拟运行；日志帮助查看操作和错误信息。
- **支持开发者**：捐赠完全自愿，不影响任何免费功能。

部分下载、搜索与安装功能需要连接第三方官方来源；网络可用性和第三方软件本身由相应项目负责。

## Windows 下载与安装

支持 Windows 10 / 11 x64。从 [v1.0.0 Release](https://github.com/kizyyyture-dev/AutoFusion-Personal/releases/tag/v1.0.0) 下载以下两个附件：

- `AutoFusionPersonal_1.0.0_Windows_x64.zip`
- `AutoFusionPersonal_1.0.0_Windows_x64.zip.sha256.txt`

在 ZIP 所在目录打开 PowerShell，运行：

```powershell
(Get-FileHash .\AutoFusionPersonal_1.0.0_Windows_x64.zip -Algorithm SHA256).Hash.ToLower()
```

结果应与校验文件中的值一致。v1.0.0 发布值为：

```text
e4da07ba9c92487cf8da15409c06961b225449f6d115c29af4dd301a62b250a9
```

解压**整个** ZIP，进入 `AutoFusionPersonal` 文件夹运行 `AutoFusionPersonal.exe`。请保留 `_internal` 目录；无需另装 Python。用户配置位于 `%LOCALAPPDATA%\AutoFusionPersonal`；发行包不包含用户的 `fusion`、`OfflinePackages` 或个人配置。

## 使用限制与注意事项

- 当前仅管理程序内已适配的模块，不支持任意软件或任意安装包的自动安装。
- 第三方官方安装器仍按原项目的安装、卸载步骤操作。
- 独立版不执行旧式源码替换自动更新。升级时从本仓库 Releases 下载新包并校验，解压到新目录；不要覆盖正在运行的旧目录。
- 在 150% 显示缩放且窗口较窄时，「设置」页部分按钮文字可能被裁切；功能不受影响。

## 安全与隐私

- 无云账户或服务器遥测；不要求注册或付费。部分功能会在用户操作时访问第三方来源。
- 已有火绒对 v1.0.0 最终 ZIP 与解压目录扫描并报告**未发现风险**；扫描记录随发行包提供。Windows Defender 扫描命令在构建机上报错，**没有 Defender 扫描结论**。
- 程序未做 Authenticode 数字签名。请勿为运行软件而关闭杀毒软件、防火墙、SmartScreen 或添加白名单。
- SHA-256 用于核对下载文件与发布值是否一致，不能代替可信发布者身份验证。PyInstaller 打包也不能保证程序无法逆向或重新封装；捐赠前请核对收款人。

## 反馈

请在本仓库 [Issues](https://github.com/kizyyyture-dev/AutoFusion-Personal/issues) 说明 Windows 版本、程序版本和复现步骤。分享日志前请删去账号、路径及其他隐私信息。

## 第三方许可与闭源声明

AutoFusion 不捆绑 OK-WW（ok-wuthering-waves）、StarRailAssistant 或 7-Zip 的程序本体；这些项目的版权、发布来源和许可归各自作者所有。具体第三方运行时及许可原文见 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) 与发行包内 `licenses` 目录。

AutoFusion 自身的使用条款见 [LICENSE.txt](LICENSE.txt)。该条款不改变第三方组件的许可。