<div align="center">

# Awesome Pets for Codex App

**English · [简体中文](./README.zh-CN.md)**

A growing collection of friendly companions for the [Codex App](https://openai.com/index/introducing-the-codex-app/).

</div>

## About

Awesome Pets is a collection of custom pets for the Codex App. These companions are here to make coding, research, and everyday tasks feel a little more cheerful.

## First to Arrive: Nai Frog

The first update introduces **Nai Frog**: a cheerful, round yellow companion with a cream-colored belly, bright green eyes, and a signature belly-holding laugh.

### All Standard States

<table>
  <tr>
    <td align="center"><strong>Idle</strong><br /><img src="./naifrog/previews/idle.png" width="160" alt="Nai Frog idle animation" /><br /><code>idle</code> · 6 frames</td>
    <td align="center"><strong>Wave</strong><br /><img src="./naifrog/previews/waving.png" width="160" alt="Nai Frog waving animation" /><br /><code>waving</code> · 4 frames</td>
    <td align="center"><strong>Belly Laugh</strong><br /><img src="./naifrog/previews/jumping.png" width="160" alt="Nai Frog belly-laugh animation in the jumping slot" /><br /><code>jumping</code> · 5 frames</td>
  </tr>
  <tr>
    <td align="center"><strong>Move Left</strong><br /><img src="./naifrog/previews/running-left.png" width="160" alt="Nai Frog moving left" /><br /><code>running-left</code> · 8 frames</td>
    <td align="center"><strong>Working</strong><br /><img src="./naifrog/previews/running.png" width="160" alt="Nai Frog working while a task is running" /><br /><code>running</code> · 6 frames</td>
    <td align="center"><strong>Move Right</strong><br /><img src="./naifrog/previews/running-right.png" width="160" alt="Nai Frog moving right" /><br /><code>running-right</code> · 8 frames</td>
  </tr>
  <tr>
    <td align="center"><strong>Needs Input</strong><br /><img src="./naifrog/previews/waiting.png" width="160" alt="Nai Frog waiting for input" /><br /><code>waiting</code> · 6 frames</td>
    <td align="center"><strong>Ready to Review</strong><br /><img src="./naifrog/previews/review.png" width="160" alt="Nai Frog reviewing completed work" /><br /><code>review</code> · 6 frames</td>
    <td align="center"><strong>Blocked</strong><br /><img src="./naifrog/previews/failed.png" width="160" alt="Nai Frog reacting to a failed or blocked task" /><br /><code>failed</code> · 8 frames</td>
  </tr>
</table>

The Codex `jumping` slot is fixed at five frames. For Nai Frog, its visuals have been customized into the signature belly laugh shown above; the slot name, frame count, and trigger behavior remain defined by Codex.

### Look Directions

<p align="center">
  <img src="./naifrog/previews/look-directions.png" width="192" alt="Nai Frog looking in 16 clockwise directions" /><br />
  <code>look directions</code> · 16 clockwise poses
</p>

When no direction vector is active, the pet falls back to its neutral or idle pose.

### Included States

| State | Frames | What Nai Frog does |
| --- | ---: | --- |
| `idle` | 6 | Rests quietly, breathes, and blinks. |
| `running-right` | 8 | Moves toward the right. |
| `running-left` | 8 | Moves toward the left. |
| `waving` | 4 | Waves to greet you or get your attention. |
| `jumping` | 5 | Performs the customized belly-laugh sequence. |
| `failed` | 8 | Slumps in response to a blocked or failed task. |
| `waiting` | 6 | Waits expectantly for approval or input. |
| `running` | 6 | Thinks and gestures while a task is running. |
| `review` | 6 | Inspects completed work that is ready to review. |

The v2 spritesheet also includes 16 clockwise look directions across its final two rows.

### Package Layout

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

- `pet.json`: pet metadata and spritesheet configuration
- `spritesheet.webp`: the animated spritesheet for Nai Frog
- `previews/`: animated README previews; these files are not required by the Codex App

## Install in the Codex App

### Option 1: Use the pet folder in Settings (recommended)

1. Download or clone this repository:

   ```bash
   git clone https://github.com/timerring/codex-pet-naiwa.git
   ```

2. Open the Codex App and go to **Settings → Pets → Custom pets**.
3. Select **Open folder** to open the local custom-pet directory.
4. Copy the repository's `naifrog` folder into that directory.
5. Return to the Codex App and select **Refresh**.
6. Select **Nai Frog**. If pets are currently hidden, select **Wake Pet**.

The final layout must be:

```text
<Codex home>/pets/
└── naifrog/
    ├── pet.json
    └── spritesheet.webp
```

Do not copy the entire `codex-pet-naiwa` repository as a nested folder under `pets`; the Codex App looks for `pet.json` directly inside each pet directory.

### Option 2: Install from a terminal

#### macOS or Linux

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

After copying the files, open **Settings → Pets** and select **Refresh**, then choose Nai Frog. Restart the Codex App if the pet does not appear after refreshing.

By default, Codex home is `~/.codex` on macOS and Linux and `$HOME\.codex` on Windows. If `CODEX_HOME` is set, the App uses that location instead.

## Credits

- [Nitrogen216/awesome_pets](https://github.com/Nitrogen216/awesome_pets) — the original Awesome Pets repository and Nai Frog Codex pet implementation on which this project is based.
- [LynnShaw/naiwa-pet](https://github.com/LynnShaw/naiwa-pet) — the source of the transparent belly-laugh frame sequence adapted for Nai Frog's `jumping` state.

## License

Original contributions in this repository are licensed under the [MIT License](LICENSE). Third-party materials identified in [Credits](#credits) are excluded and remain subject to their respective owners' rights.
