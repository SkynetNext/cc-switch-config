# CC Switch + Claude Code 配置教程

> 使用 AIGoCode 中转（支持支付宝/微信，国内直连）

---

## 一、安装 CC Switch

PowerShell 执行（便携版，解压到桌面）：

```powershell
Invoke-WebRequest -Uri "https://github.com/farion1231/cc-switch/releases/download/v3.11.1/CC-Switch-v3.11.1-Windows-Portable.zip" -OutFile "$env:USERPROFILE\Downloads\CC-Switch-Portable.zip" -UseBasicParsing
Expand-Archive -Path "$env:USERPROFILE\Downloads\CC-Switch-Portable.zip" -DestinationPath "$env:USERPROFILE\Desktop\CC-Switch" -Force
Start-Process "$env:USERPROFILE\Desktop\CC-Switch\cc-switch.exe"
```

> 新版本请到 [Releases](https://github.com/farion1231/cc-switch/releases/latest) 查看，替换 URL 中的版本号。

---

## 二、注册 AIGoCode 并创建 API Key

1. 打开 https://aigocode.com 注册、充值（最低 ¥50 按量）
2. 进入 **API Key 管理** → 分组选 **Claude Max（专用型）**（Claude Code 首选，1.8 块/1 美元）
3. 点击卡片创建 Key，可「一键导入 CC Switch」或复制备用

---

## 三、CC Switch 配置

1. 选择 **Claude** 分组 → 点击 **+** 添加提供商 → 选 **AIGoCode** 预设
2. 粘贴 API Key，其余配置保持默认
3. 保存后点击 **「启用」**，状态为「使用中」即生效

---

## 四、VSCode 插件同步（重要）

要在 VSCode Claude Code 插件中使用，必须开启：

**设置（齿轮）→ 通用 → 「应用到 Claude Code 插件」→ 打开**

---

## 五、验证

- **VSCode**：安装 Claude Code 插件，重启后使用

---
