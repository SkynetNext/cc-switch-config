# CC Switch + Claude Code 配置教程

> 使用 AIGoCode 中转（支持支付宝/微信，国内直连）

---

## 一、环境

需 Node.js ≥ 18（`winget install OpenJS.NodeJS`）。终端用 Claude Code 需先执行 `npm install -g @anthropic-ai/claude-code`。

---

## 二、安装 CC Switch

PowerShell 执行（便携版，解压到桌面）：

```powershell
Invoke-WebRequest -Uri "https://github.com/farion1231/cc-switch/releases/download/v3.11.1/CC-Switch-v3.11.1-Windows-Portable.zip" -OutFile "$env:USERPROFILE\Downloads\CC-Switch-Portable.zip" -UseBasicParsing
Expand-Archive -Path "$env:USERPROFILE\Downloads\CC-Switch-Portable.zip" -DestinationPath "$env:USERPROFILE\Desktop\CC-Switch" -Force
Start-Process "$env:USERPROFILE\Desktop\CC-Switch\cc-switch.exe"
```

> 新版本请到 [Releases](https://github.com/farion1231/cc-switch/releases/latest) 查看，替换 URL 中的版本号。

---

## 三、注册 AIGoCode 并创建 API Key

1. 打开 https://aigocode.com 注册、充值（最低 ¥50 按量）
2. 进入 **API Key 管理** → 分组选 **Claude Max（专用型）**（Claude Code 首选，1.8 块/1 美元）
3. 点击卡片创建 Key，可「一键导入 CC Switch」或复制备用

---

## 四、CC Switch 配置

1. 选择 **Claude** 分组 → 点击 **+** 添加提供商 → 选 **AIGoCode** 预设
2. 粘贴 API Key，请求地址一般为 `https://api.aigocode.com`（勿以 `/` 结尾）
3. **模型配置**：CC Switch 的 AIGoCode 预设未指定模型，Claude Code 会使用默认 `claude-sonnet-4-5`，而 AIGoCode 可能不支持该 ID。在编辑供应商页的 **Sonnet 默认模型** 或 **主模型** 中填入 AIGoCode 支持的模型，例如：
   - `claude-sonnet-4-6`（AIGoCode 官网标注支持 Claude 4.6）
   - 或 `claude-sonnet-4`（若 4.6 不可用）
   - 具体以 [AIGoCode 文档](https://www.aigocode.com/docs) 或控制台为准
4. 保存后点击 **「启用」**，状态为「使用中」即生效

---

## 五、VSCode 插件同步（重要）

要在 VSCode Claude Code 插件中使用，必须开启：

**设置（齿轮）→ 通用 → 「应用到 Claude Code 插件」→ 打开**

---

## 六、验证

- **终端**：运行 `claude`，能对话即成功
- **VSCode**：安装 Claude Code 插件，重启后使用

---

## 常见问题

- **找不到「应用到 Claude Code 插件」**：设置 → 通用 → 窗口行为区域
- **VSCode 仍要登录**：确认已开启该选项并重启 VSCode
- **Base URL 拼写**：`ANTHROPIC_BASE_URL`、`api.aigocode.com`（非 apt）
