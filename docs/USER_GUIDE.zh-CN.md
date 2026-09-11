# Windows Fader Bridge for EUCON 使用手册

[English](USER_GUIDE.en.md) ・ [日本語](USER_GUIDE.ja.md) ・ [返回主页](../README.md)

## 它能做什么

本程序把 Windows 音量混音器变成一个独立的 EUCON 应用。你可以在 Avid S3、其他兼容控制台或 Avid Control 上控制主输出、输入设备和正在发声的 Windows 应用。

它不会替代 EuControl，也不会改变声卡驱动。音量、声像、静音、独奏、选择、峰值表和电机推子反馈会实时同步。

## 使用前准备

- Windows 11 64 位。
- 已安装并能正常运行的 Avid EuControl / EUCON Workstation 2026.4。
- 已在 EuControl 中正常连接的 EUCON 控制台，或装有 Avid Control 的平板。

## 安装

1. 在 [Releases](https://github.com/lindelea/windows-fader-bridge-eucon/releases/latest) 下载名称以 `Setup-x64.exe` 结尾的安装程序。
2. 退出以前手动运行的便携版，双击安装程序并按提示完成安装。
3. 安装程序会一并准备所需的 Microsoft Visual C++ 运行库。
4. 从开始菜单打开 **Windows Fader Bridge for EUCON**。

本项目暂未购买 Windows 代码签名证书，因此 Windows 可能显示“未知发布者”。请只从本仓库的 Releases 下载，并可用发布页中的 SHA-256 校验值核对文件。

## 第一次连接

1. 先确认 EuControl 已运行、控制台显示在线。
2. 启动本程序。主界面显示“控制器已连接”后即可使用。
3. 如果 EuControl 当前在控制其他软件，把本程序窗口调到前台一次，或按 `Ctrl+Alt+Shift+W`，EUCON 焦点就会切到本程序。
4. 需要经常在 Cubase、Windows 音频和 UAD Console 之间切换时，可在 EuControl 的 Soft Keys 中选择本应用提供的 **Windows EUCON**、**UAD EUCON** 等命令，再分配到实体键。

程序与 Windows 音频服务、EUCON 的启动顺序不再是硬性要求；开机时服务尚未准备好，程序会自动等待并重连。

## 日常操作

- 推子：通道音量；Master 对应 Windows 默认输出。
- 声像旋钮：左右声像或立体声平衡；按下回到中心。
- Mute / Solo：控制并显示 Windows 的真实状态。
- Bank：翻到上一组或下一组在线通道。
- 峰值表：显示 Windows 当前音频电平，不是装饰动画。
- 在程序总览页点击一行，可选择对应通道。

Windows 应用关闭后会从在线通道中移除；再次出现时会按稳定身份恢复。正在触摸推子时，通道列表变化不会把这次手势转移到另一个应用。

## 设置与后台运行

“设置”中可以选择中英文界面、随 Windows 启动、关闭窗口后留在托盘、全局调出快捷键，以及调出后是否自动回到后台。默认快捷键是 `Ctrl+Alt+Shift+W`，也可以重新录制，但不要与其他软件的全局快捷键重复。

关闭窗口通常只是隐藏到系统托盘。需要完全退出或重新连接时，右击托盘图标选择相应命令。

## 常见问题

**控制台看不到本程序**：确认 EuControl 与本程序都在运行；在 EuControl 的 Applications 页面确认应用存在，然后按全局调出快捷键。

**某个应用没有声音通道**：该应用需要先建立 Windows 音频会话，通常播放一下声音即可出现。

**推子弹回或不同步**：确认没有另一个程序同时控制同一 Windows 会话；从托盘选择“重新启动”后再试。若持续发生，请在设置中打开日志文件夹并随错误报告附上最新日志。

**卸载**：打开 Windows“设置 → 应用 → 已安装的应用”，找到本程序并选择卸载。个人设置会保留，方便重新安装；不需要时可手动删除 `%LOCALAPPDATA%` 下对应的设置目录。

## 报告问题

请前往 [GitHub Issues](https://github.com/lindelea/windows-fader-bridge-eucon/issues)，说明 Windows、EuControl 和控制台型号/版本、复现步骤及实际现象。日志可能包含本机应用和设备名称，上传前请先检查。
