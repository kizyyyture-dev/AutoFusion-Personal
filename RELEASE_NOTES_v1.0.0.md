# AutoFusion Personal V1.0.0 — Release 说明

**平台**：Windows 10 / 11 x64。目录版 ZIP，解压后运行 `AutoFusionPersonal.exe`，无需另装 Python。

## 下载与校验

| 文件 | 用途 |
| --- | --- |
| `AutoFusionPersonal_1.0.0_Windows_x64.zip` | Windows x64 发行包（11,523,043 字节） |
| `AutoFusionPersonal_1.0.0_Windows_x64.zip.sha256.txt` | ZIP 的 SHA-256 校验文件 |

```text
e4da07ba9c92487cf8da15409c06961b225449f6d115c29af4dd301a62b250a9  AutoFusionPersonal_1.0.0_Windows_x64.zip
```

在 PowerShell 中运行 `(Get-FileHash .\AutoFusionPersonal_1.0.0_Windows_x64.zip -Algorithm SHA256).Hash.ToLower()`，与上述值核对。SHA-256 只能核对文件与发布值是否一致，不能代替发布者身份验证。

## 本版功能

AutoFusion Personal 是 Windows 本地工具统一管理平台，为**已适配**的第三方软件提供集中的下载、安装、启动和管理入口。实际操作取决于模块适配方式：官方安装器项目沿用原版安装与卸载流程，便携包项目可按受管文件清单管理。

本版提供模块状态管理、离线安装包库、只读软件目录诊断、默认模拟运行的任务队列和运行日志。离线库不会自动安装任意导入文件。部分功能需要连接第三方官方来源。支持开发者捐赠完全自愿，不影响免费功能。

## 验证与安全状态

- 本机构建后**共运行 125 项测试，其中跳过 4 项，0 项失败**。
- 火绒安全软件 6.0.12.3（病毒库 2026-10-29 19:42）分别扫描解压目录与最终 ZIP，记录为**未发现风险**；记录见发行包内 `安全扫描状态.txt`。扫描时未关闭实时防护或添加白名单。
- Windows 11 26100 实机复验了五个页面、两张收款码、关闭及重新启动。
- Windows Defender 扫描命令在构建机上报错（“Errors were encountered when attempted to scan your device.”），**没有 Defender 扫描结论**。
- 程序**未做 Authenticode 数字签名**。请勿关闭杀毒软件、防火墙或 SmartScreen。

## 已知限制与升级

- 当前仅支持程序内已适配模块，不支持任意软件或任意安装包的自动安装。
- 150% 显示缩放且窗口较窄时，「设置」页部分按钮文字可能被裁切，功能不受影响。
- 独立版不执行旧式源码替换自动更新。从本仓库 Releases 获取新版本并核对哈希，解压到新目录，不要覆盖正在运行的旧目录。用户配置位于 `%LOCALAPPDATA%\AutoFusionPersonal`；已有模块与离线库不会随解压自动搬迁或清理。
- PyInstaller 打包不能保证无法逆向或重新封装；扫码捐赠前请核对收款人。第三方项目的版权与许可归各自作者所有。