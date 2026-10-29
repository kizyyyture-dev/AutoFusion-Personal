# 第三方组件与许可（AutoFusion Personal V1.0.0）

本程序用 PyInstaller 打包为独立的 Windows 目录版，运行时不要求用户安装 Python。
下列组件随发行包一起分发，其许可原文放在发行包内的 `licenses\` 目录，并随本仓库一并提供副本。

| 组件 | 随包版本 | 许可 | 许可原文（包内 `licenses\`） | 来源 |
| --- | --- | --- | --- | --- |
| Python | 3.13.12 | PSF License Agreement 2.0 | `Python-LICENSE.txt` | https://www.python.org/ |
| Tcl / Tk | 8.6 | Tcl/Tk License（BSD 式） | `Tcl-Tk-license.terms` | https://www.tcl.tk/ |
| OpenSSL | 3.0.18（libcrypto-3.dll / libssl-3.dll） | Apache License 2.0 | `OpenSSL-Apache-2.0.txt` | https://www.openssl.org/ |
| zlib | 1.3.1（zlib1.dll） | zlib License | `zlib-LICENSE.txt` | https://zlib.net/ |
| libffi | 3.4.6（libffi-8.dll） | MIT License | `libffi-LICENSE.txt` | https://github.com/libffi/libffi |
| PyInstaller（bootloader） | 6.22.3 | GPL-2.0-or-later + Bootloader Exception | `PyInstaller-COPYING.txt` | https://pyinstaller.org/ |
| MSVC / UCRT 运行库（VCRUNTIME140.dll、VCRUNTIME140_1.dll、ucrtbase.dll、api-ms-win-*） | 随构建环境 | Microsoft Visual C++ 可再发行组件条款（非开源许可，未修改） | `VC运行库说明.txt` | https://learn.microsoft.com/cpp/windows/latest-supported-vc-redist |
| CPython 静态编入的第三方代码（expat、bzip2、liblzma、libmpdec、HACL* 等） | 随 Python 3.13.12 | 各自许可，说明见文件 | `CPython-其他组件说明.txt` | https://www.python.org/ |

补充说明：

- 逐项对应关系、版权行与获取链接另见包内 `licenses\README-许可说明.txt`。
- 本程序**不捆绑** OK-WW、StarRailAssistant、7-Zip；这些工具由用户通过各自作者的官方渠道下载安装，遵循其自身许可。
- SQLite 未随本包分发（`_internal` 中无 `_sqlite3.pyd`），因此未附 SQLite 的公有领域声明。
- PyInstaller 以 GPL-2.0-or-later 及其 Bootloader Exception 授权；本程序通过其 bootloader 打包，符合该例外条款。
- 如对许可归属有疑问，请以对应组件官方发布的许可原文为准。
