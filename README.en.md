<div align="center">

# Nai Frog for Codex

**[简体中文](./README.md) · English**

A custom Nai Frog / Naiwa Pet for the [Codex App](https://openai.com/index/introducing-the-codex-app/).

</div>

## Quick Install

Send this instruction to Codex:

> Install the Nai Frog pet from https://github.com/timerring/codex-pet-naiwa by copying the `naifrog` folder into my custom pets directory, then tell me how to refresh and enable it in Codex.

## Animation Preview

<table>
  <tr>
    <td align="center"><strong>Idle</strong><br /><img src="./naifrog/previews/idle.png" width="160" alt="Nai Frog idle animation" /><br /><code>idle</code> · 6 frames</td>
    <td align="center"><strong>Wave</strong><br /><img src="./naifrog/previews/waving.png" width="160" alt="Nai Frog waving animation" /><br /><code>waving</code> · 4 frames</td>
    <td align="center"><strong>Belly Laugh</strong><br /><img src="./naifrog/previews/jumping.png" width="160" alt="Nai Frog belly-laugh animation" /><br /><code>jumping</code> · 5 frames</td>
  </tr>
  <tr>
    <td align="center"><strong>Move Left</strong><br /><img src="./naifrog/previews/running-left.png" width="160" alt="Nai Frog moving left" /><br /><code>running-left</code> · 8 frames</td>
    <td align="center"><strong>Working</strong><br /><img src="./naifrog/previews/running.png" width="160" alt="Nai Frog working animation" /><br /><code>running</code> · 6 frames</td>
    <td align="center"><strong>Move Right</strong><br /><img src="./naifrog/previews/running-right.png" width="160" alt="Nai Frog moving right" /><br /><code>running-right</code> · 8 frames</td>
  </tr>
  <tr>
    <td align="center"><strong>Needs Input</strong><br /><img src="./naifrog/previews/waiting.png" width="160" alt="Nai Frog waiting for input" /><br /><code>waiting</code> · 6 frames</td>
    <td align="center"><strong>Ready to Review</strong><br /><img src="./naifrog/previews/review.png" width="160" alt="Nai Frog ready for review" /><br /><code>review</code> · 6 frames</td>
    <td align="center"><strong>Failed or Blocked</strong><br /><img src="./naifrog/previews/failed.png" width="160" alt="Nai Frog failed or blocked animation" /><br /><code>failed</code> · 8 frames</td>
  </tr>
</table>

`jumping` is the fixed Codex state name; this pet displays it as a belly laugh.

## Look Directions

<p align="center">
  <img src="./naifrog/previews/look-directions.png" width="192" alt="Nai Frog looking in 16 directions" /><br />
  <code>look directions</code> · 16 directions
</p>

## Manual Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/timerring/codex-pet-naiwa.git
   ```

2. Open **Settings → Pets → Custom pets → Open folder** in the Codex App.
3. Copy the repository's `naifrog` folder into the opened directory.
4. Return to the Codex App, select **Refresh**, then choose Nai Frog.

### Command Line

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

## Files

```text
naifrog/
├── pet.json
├── spritesheet.webp
└── previews/
```

- `pet.json`: pet metadata
- `spritesheet.webp`: Codex v2 animation spritesheet
- `previews/`: README animation previews; not required by the pet

## Credits

- [Nitrogen216/awesome_pets](https://github.com/Nitrogen216/awesome_pets)
- [LynnShaw/naiwa-pet](https://github.com/LynnShaw/naiwa-pet)

## License

Original content in this repository is licensed under the [MIT License](LICENSE). Third-party materials listed under Credits are excluded from the MIT license.
