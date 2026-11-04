# PuTTY WebView

PuTTY WebView 是基于 PuTTY 0.85 的 Windows 终端客户端，使用 WebView2 和 xterm.js 提供多会话界面。本项目为非官方衍生项目，与 PuTTY 官方项目无隶属关系。

## 安全提示

本版本合并了 PuTTY 0.85 的上游更新，包括官方公布的安全修复。衍生项目的改动仍需独立验证；请参阅 [PuTTY 0.85 官方发布说明](https://www.chiark.greenend.org.uk/~sgtatham/putty/releases/0.85.html)。

## 功能

- 支持 PuTTY 会话，以及本地 PowerShell 和 WSL 终端。
- 多标签、拖拽、分屏和跨窗口停靠。
- 输入发送速率限制，适合接收缓冲较小的串口设备。
- 支持 OpenSSH 和 ssh.com 格式私钥导入、会话日志目录配置。
- 基于 WebView2 的深色界面和浮动编辑器。

## 安装和运行

Windows x64 用户可从项目 Releases 下载 MSI 安装包。需要预先安装 Microsoft Edge WebView2 Runtime。安装范围为当前用户，默认安装到 `%LOCALAPPDATA%\Programs\PuTTY-WebView`。便携运行时，须将 `webview` 资源目录与 `putty_webview.exe` 放在一起。详见 [安装说明](docs/WEBVIEW-INSTALLER.md)。

## 构建

使用 Visual Studio 2022、Windows SDK、CMake 和 WebView2 SDK，执行：

```powershell
.\build.bat putty_webview
.\build-msi.ps1 -Version 1.0.0
```

MSI 打包需要 WiX 3.14，路径和签名要求见[安装说明](docs/WEBVIEW-INSTALLER.md)。

## 源码与许可

本项目基于 [PuTTY 官方源码](https://git.tartarus.org/simon/putty.git)，保留官方历史与 `0.84` 标签；PuTTY WebView 1.0.0 导入之后合并了上游 0.85。原项目说明见 [README](README)，许可条款见 [LICENCE](LICENCE)。本仓库包含第三方资源，请同时遵守各组件自带的许可条款。
