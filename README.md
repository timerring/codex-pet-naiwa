<div align="center">

# Codex 奶蛙桌宠

**简体中文 · [English](./README.en.md)**

一个为 Codex 打造的奶龙 / 奶蛙桌面宠物 Naifrog / Naiwa Codex pet

</div>

## 快速安装

将下面这句话发送给 Codex：

> 请帮我安装这个 Codex 奶蛙桌宠：<https://github.com/timerring/codex-pet-naiwa>，将 `naifrog` 文件夹复制到我的自定义宠物目录，并告诉我如何刷新和启用它。

## 动画预览

<table>
  <tr>
    <td align="center"><strong>待机</strong><br /><img src="./naifrog/previews/idle.png" width="160" alt="奶蛙待机动画" /><br /><code>idle</code> · 6 帧</td>
    <td align="center"><strong>招手</strong><br /><img src="./naifrog/previews/waving.png" width="160" alt="奶蛙招手动画" /><br /><code>waving</code> · 4 帧</td>
    <td align="center"><strong>捧腹大笑</strong><br /><img src="./naifrog/previews/jumping.png" width="160" alt="奶蛙捧腹大笑动画" /><br /><code>jumping</code> · 5 帧</td>
  </tr>
  <tr>
    <td align="center"><strong>向左移动</strong><br /><img src="./naifrog/previews/running-left.png" width="160" alt="奶蛙向左移动" /><br /><code>running-left</code> · 8 帧</td>
    <td align="center"><strong>执行任务</strong><br /><img src="./naifrog/previews/running.png" width="160" alt="奶蛙执行任务动画" /><br /><code>running</code> · 6 帧</td>
    <td align="center"><strong>向右移动</strong><br /><img src="./naifrog/previews/running-right.png" width="160" alt="奶蛙向右移动" /><br /><code>running-right</code> · 8 帧</td>
  </tr>
  <tr>
    <td align="center"><strong>等待输入</strong><br /><img src="./naifrog/previews/waiting.png" width="160" alt="奶蛙等待输入动画" /><br /><code>waiting</code> · 6 帧</td>
    <td align="center"><strong>完成待查看</strong><br /><img src="./naifrog/previews/review.png" width="160" alt="奶蛙完成待查看动画" /><br /><code>review</code> · 6 帧</td>
    <td align="center"><strong>失败或阻塞</strong><br /><img src="./naifrog/previews/failed.png" width="160" alt="奶蛙失败或阻塞动画" /><br /><code>failed</code> · 8 帧</td>
  </tr>
</table>

## 注视方向

<p align="center">
  <img src="./naifrog/previews/look-directions.png" width="192" alt="奶蛙的 16 个注视方向" /><br />
  <code>look directions</code> · 16 个方向
</p>

## 桌面端安装与启用

> [!NOTE]
> ChatGPT 桌面端使用本地自定义宠物目录，不提供 Web 端的 **Upload pet** 上传流程。桌面端与 Web 端的自定义宠物分开管理；安装到桌面端的奶蛙不会自动同步到 Web。

### 通过设置页面安装

1. 克隆仓库：

   ```bash
   git clone https://github.com/timerring/codex-pet-naiwa.git
   ```

2. 打开 ChatGPT 桌面端，进入 **Settings → Pets → Custom pets → Open folder**。
3. 将仓库中的 `naifrog` 文件夹复制到打开的目录。
4. 返回 **Settings → Pets**，点击 **Refresh**。
5. 找到奶蛙并点击 **Select**。
6. 点击 **Wake Pet**，或在命令菜单中运行 `/pet`，让奶蛙显示在桌面上。

桌面端会记住选择和宠物位置。再次运行 `/pet`，或选择 **Tuck Away Pet**，可以隐藏奶蛙。完整行为可参考 [OpenAI Pets 官方文档](https://learn.chatgpt.com/docs/pets)。

### 命令行安装

#### macOS / Linux

```bash
git clone https://github.com/timerring/codex-pet-naiwa.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/pets/naifrog"
cp -R codex-pet-naiwa/naifrog/. "${CODEX_HOME:-$HOME/.codex}/pets/naifrog/"
```

#### Windows PowerShell

```powershell
git clone https://github.com/timerring/codex-pet-naiwa.git
$codexHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $HOME ".codex" }
$petDir = Join-Path $codexHome "pets\naifrog"
New-Item -ItemType Directory -Force $petDir | Out-Null
Copy-Item ".\codex-pet-naiwa\naifrog\*" $petDir -Recurse -Force
```

命令执行完成后，仍需回到桌面端完成 **Refresh → Select → Wake Pet**。

### 关于 Web 端

本仓库的 `spritesheet.webp` 是桌面端 v2 素材（`1536 × 2288`）。Web 端需要在 **Settings → Personalization → Pet → Upload pet** 中单独上传 `1536 × 1872` 的透明 PNG 或 WebP，因此不能直接使用本仓库的 v2 精灵表上传。

## 文件结构

```text
naifrog/
├── pet.json
├── spritesheet.webp
└── previews/
```

- `pet.json`：桌宠元数据
- `spritesheet.webp`：Codex v2 动画精灵表
- `previews/`：README 动画预览，不影响桌宠运行

## Credits / 致谢

- [Nitrogen216/awesome_pets](https://github.com/Nitrogen216/awesome_pets)
- [LynnShaw/naiwa-pet](https://github.com/LynnShaw/naiwa-pet)

## 许可证

本仓库原创内容使用 [MIT License](LICENSE)。Credits 中的第三方素材不在 MIT 授权范围内。
