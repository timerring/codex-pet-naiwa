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

## 手动安装

1. 克隆仓库：

   ```bash
   git clone https://github.com/timerring/codex-pet-naiwa.git
   ```

2. 打开 Codex App，进入 **Settings → Pets → Custom pets → Open folder**。
3. 将仓库中的 `naifrog` 文件夹复制到打开的目录。
4. 返回 Codex App，点击 **Refresh**，然后选择奶蛙。

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
- [Linux Do](https://linux.do/)

## 许可证

本仓库原创内容使用 [MIT License](LICENSE)。Credits 中的第三方素材不在 MIT 授权范围内。
