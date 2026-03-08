# 🔊 Debug Error Sound

A VS Code extension that plays custom sounds when errors or exceptions occur during debugging — so you never miss a bug!

---

## ✨ Features

- 🚨 **Exception Detection** — plays a sound when an exception is thrown during a debug session
- ⏸️ **Breakpoint Hit** — optional sound when a breakpoint is reached
- 🎵 **4 Sound Profiles** — Classic, Retro, Subtle, and Dramatic
- 🔉 **Volume Control** — adjust the volume to your preference
- 📁 **Custom Sound File** — use your own `.wav` or `.mp3` file
- 💻 **Cross-platform** — works on Windows, macOS, and Linux
- 🟢 **Status Bar Indicator** — shows active sound profile in the status bar

---

## 🚀 Getting Started

1. Install the extension
2. Start a debug session (`F5`)
3. Trigger an exception or hit a breakpoint — you'll hear a sound!

---

## ⚙️ Configuration

Open VS Code Settings (`Ctrl+,`) and search for **"Debug Error Sound"**:

| Setting | Default | Description |
|---|---|---|
| `debugErrorSound.enabled` | `true` | Enable/disable all sounds |
| `debugErrorSound.soundProfile` | `"classic"` | Sound theme: `classic`, `retro`, `subtle`, `dramatic` |
| `debugErrorSound.volume` | `0.8` | Volume from `0.0` to `1.0` |
| `debugErrorSound.playOnBreakpoint` | `true` | Play sound on breakpoint hits |
| `debugErrorSound.playOnException` | `true` | Play sound on exceptions |
| `debugErrorSound.customSoundPath` | `""` | Path to custom `.wav`/`.mp3` file |

---

## 🎵 Sound Profiles

| Profile | Description |
|---|---|
| **Classic** | Double-beep error sound — familiar and clear |
| **Retro** | Descending 8-bit style chime |
| **Subtle** | Soft two-tone chime for quiet environments |
| **Dramatic** | Descending alarm — you won't miss this one! |

---

## 🧪 Commands

Open the Command Palette (`Ctrl+Shift+P`) and search:

- **`Debug Error Sound: Test Sound`** — Play the current sound profile
- **`Debug Error Sound: Select Sound Profile`** — Choose a profile from a menu

---

## 💡 How It Works

The extension uses VS Code's Debug Adapter Protocol (DAP) tracker to intercept debug session messages. When a `stopped` event with reason `exception`, `unhandledException`, or a stderr output event is received, it triggers the configured sound.

### Platform Sound Methods

| Platform | Method |
|---|---|
| **Windows** | PowerShell `[console]::beep()` for built-in; `Media.SoundPlayer` for custom files |
| **macOS** | `osascript` + `afplay` for system sounds; `afplay` for custom files |
| **Linux** | `beep` command or `aplay` for WAV files |

---

## 📦 Building from Source

```bash
git clone https://github.com/onlygoku/debug-error-sound
cd debug-error-sound
npm install
npm run compile
```

To launch in development mode, press `F5` in VS Code with this project open.

---

## 📝 License

MIT License — see [LICENSE](LICENSE) for details.