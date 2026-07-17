<div align="center">

# Codex App 奶蛙桌宠

**[English](./README.md) · 简体中文**

一个可直接安装到 [Codex App](https://openai.com/index/introducing-the-codex-app/) 的奶蛙自定义桌宠，用动画回应不同任务状态。

</div>

## 关于本项目

本仓库将 **奶蛙（Nai Frog）**打包为 Codex App 自定义桌宠。`naifrog` 目录包含桌宠元数据和 Codex v2 精灵表，README 中的预览则完整展示了各个任务状态在 App 中对应的动画效果。

当 Codex 处于待机、执行任务、等待输入、完成待查看、失败阻塞或左右移动等状态时，奶蛙会播放相应动作；其中 `jumping` 槽位被定制成了它标志性的捧腹大笑。

## 认识奶蛙

**奶蛙**是一只开朗、圆润的黄色小伙伴，拥有奶油色肚皮和绿色大眼睛。它会在待机时呼吸眨眼，在 Codex 工作时专注比划，在需要输入时耐心等待，在任务受阻时作出反应，还能左右移动，并用捧腹大笑庆祝进展。

### 全部标准状态

<table>
  <tr>
    <td align="center"><strong>待机</strong><br /><img src="./naifrog/previews/idle.png" width="160" alt="奶蛙待机动画" /><br /><code>idle</code> · 6 帧</td>
    <td align="center"><strong>招手</strong><br /><img src="./naifrog/previews/waving.png" width="160" alt="奶蛙招手动画" /><br /><code>waving</code> · 4 帧</td>
    <td align="center"><strong>捧腹大笑</strong><br /><img src="./naifrog/previews/jumping.png" width="160" alt="奶蛙在 jumping 槽位中的捧腹大笑动画" /><br /><code>jumping</code> · 5 帧</td>
  </tr>
  <tr>
    <td align="center"><strong>向左移动</strong><br /><img src="./naifrog/previews/running-left.png" width="160" alt="奶蛙向左移动" /><br /><code>running-left</code> · 8 帧</td>
    <td align="center"><strong>执行任务</strong><br /><img src="./naifrog/previews/running.png" width="160" alt="奶蛙在任务运行时工作" /><br /><code>running</code> · 6 帧</td>
    <td align="center"><strong>向右移动</strong><br /><img src="./naifrog/previews/running-right.png" width="160" alt="奶蛙向右移动" /><br /><code>running-right</code> · 8 帧</td>
  </tr>
  <tr>
    <td align="center"><strong>等待输入</strong><br /><img src="./naifrog/previews/waiting.png" width="160" alt="奶蛙等待用户输入" /><br /><code>waiting</code> · 6 帧</td>
    <td align="center"><strong>完成待查看</strong><br /><img src="./naifrog/previews/review.png" width="160" alt="奶蛙查看已完成的工作" /><br /><code>review</code> · 6 帧</td>
    <td align="center"><strong>失败或阻塞</strong><br /><img src="./naifrog/previews/failed.png" width="160" alt="奶蛙对任务失败或阻塞作出反应" /><br /><code>failed</code> · 8 帧</td>
  </tr>
</table>

Codex 的 `jumping` 槽位固定使用 5 帧。奶蛙把这个槽位的画面定制成了上面的标志性捧腹大笑；槽位名称、帧数和触发逻辑仍由 Codex 定义。

### 注视方向

<p align="center">
  <img src="./naifrog/previews/look-directions.png" width="192" alt="奶蛙按顺时针查看 16 个方向" /><br />
  <code>look directions</code> · 16 个顺时针方向姿势
</p>

没有方向向量时，桌宠会回到 neutral 或 idle 姿势。

### 包含的状态

| 状态 | 帧数 | 奶蛙的表现 |
| --- | ---: | --- |
| `idle` | 6 | 安静站立、呼吸和眨眼。 |
| `running-right` | 8 | 向右移动。 |
| `running-left` | 8 | 向左移动。 |
| `waving` | 4 | 招手问候或吸引你的注意。 |
| `jumping` | 5 | 播放定制后的捧腹大笑动作。 |
| `failed` | 8 | 在任务失败或阻塞时逐渐低头、泄气。 |
| `waiting` | 6 | 期待地等待你的批准或输入。 |
| `running` | 6 | 在任务运行时专注思考并用手比划。 |
| `review` | 6 | 查看已经完成、等待检查的工作。 |

v2 精灵表的最后两行还包含按顺时针排列的 16 个注视方向。

### 目录结构

```text
naifrog/
├── pet.json
├── spritesheet.webp
└── previews/
    ├── failed.png
    ├── idle.png
    ├── jumping.png
    ├── look-directions.png
    ├── review.png
    ├── running-left.png
    ├── running-right.png
    ├── running.png
    ├── waiting.png
    └── waving.png
```

- `pet.json`：宠物信息及精灵图配置
- `spritesheet.webp`：奶蛙的动画精灵图
- `previews/`：README 使用的动画预览，Codex App 本身不依赖这些文件

## 安装到 Codex App

### 方法一：通过设置中的宠物目录安装（推荐）

1. 下载或克隆本仓库：

   ```bash
   git clone https://github.com/timerring/codex-pet-naiwa.git
   ```

2. 打开 Codex App，进入 **Settings → Pets → Custom pets**。
3. 点击 **Open folder**，打开本地自定义宠物目录。
4. 将仓库中的 `naifrog` 文件夹复制到该目录中。
5. 返回 Codex App，点击 **Refresh**。
6. 选择 **奶蛙（Nai Frog）**。如果宠物当前处于隐藏状态，请点击 **Wake Pet**。

最终目录结构必须是：

```text
<Codex 主目录>/pets/
└── naifrog/
    ├── pet.json
    └── spritesheet.webp
```

不要把整个 `codex-pet-naiwa` 仓库作为嵌套文件夹复制到 `pets` 中；Codex App 会直接在每个宠物目录下查找 `pet.json`。

### 方法二：通过终端安装

#### macOS 或 Linux

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

复制完成后，请进入 **Settings → Pets**，点击 **Refresh** 并选择奶蛙。如果刷新后仍未出现，请重启 Codex App。

默认情况下，macOS 和 Linux 的 Codex 主目录是 `~/.codex`，Windows 中是 `$HOME\.codex`。如果设置了 `CODEX_HOME`，App 将使用该位置。

## Credits / 致谢

- [Nitrogen216/awesome_pets](https://github.com/Nitrogen216/awesome_pets) — 本项目所基于的原始 Awesome Pets 仓库及奶蛙 Codex 桌宠实现。
- [LynnShaw/naiwa-pet](https://github.com/LynnShaw/naiwa-pet) — 奶蛙 `jumping` 状态中捧腹大笑透明动画帧序列的来源。

## 许可证

本仓库中的原创贡献采用 [MIT License](LICENSE)。[Credits / 致谢](#credits--致谢)中列明的第三方素材不包含在此授权范围内，其权利仍归各自权利人所有。
