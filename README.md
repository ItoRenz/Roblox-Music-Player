# 🎵 Roblox Music Player

Advanced music player with persistent state, loop modes, and mobile support for Roblox games.

![Version](https://img.shields.io/badge/version-1.0.3-blue.svg)
![Roblox](https://img.shields.io/badge/platform-Roblox-red.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📋 Features

- ✅ **Auto-play on First Join** - Music starts automatically when player joins for the first time
- 💾 **Persistent State** - Saves playback state, volume, and position across sessions
- 🔁 **Multiple Loop Modes** - Loop All, Loop One, or No Loop
- 📱 **Mobile & Desktop Support** - Responsive UI for all devices
- 💀 **Death-Proof** - Music continues playing even when character dies
- 🎚️ **Volume Control** - Adjustable volume from 0-10
- ⏯️ **Full Playback Controls** - Play, Pause, Next, Previous
- 📊 **Progress Bar** - Visual timeline with current position
- 🎨 **Modern UI Design** - Clean, glassmorphism-inspired interface

## 📦 Installation

1. Open Roblox Studio
2. Navigate to: `StarterPlayer > StarterPlayerScripts`
3. Create a new `LocalScript`
4. Paste the music player code
5. Customize the `musicList` array with your audio IDs

## 🎼 Adding Your Music

Edit the `musicList` table in the script:

```lua
local musicList = {
    {id = "rbxassetid://YOUR_AUDIO_ID", title = "Song Title"},
    {id = "rbxassetid://YOUR_AUDIO_ID", title = "Another Song"},
    -- Add more songs...
}
```

## 🎮 Usage

### For Players

- **Toggle UI**: Click the "MUSIC" button in the top center
- **Play/Pause**: Click the play button (▶️/⏸️)
- **Next/Previous**: Use arrow buttons (⏮️/⏭️)
- **Loop Mode**: Click loop button (🔁/🔂) to cycle through modes
- **Volume**: Enter a number (0-10) in the volume box

### Loop Modes

| Mode | Icon | Description |
|------|------|-------------|
| **Loop All** | 🔁 | Plays all songs in sequence, repeating playlist |
| **Loop One** | 🔂 | Repeats current song indefinitely |
| **Loop Off** | 🔁 (gray) | Stops after playlist ends |

## 🔧 Configuration

### Volume Range
Default volume is `5` (range: 0-10)
```lua
volume = 5  -- Adjust in state initialization
```

### UI Position (Desktop)
```lua
Position = UDim2.new(0.5, -190, 0, 12)  -- Top center-left
```

### UI Position (Mobile)
```lua
Position = UDim2.new(0.5, -15, 0, 12)  -- Top center
```

## 📊 Technical Details

### State Management
Uses global `_G.MusicPlayerData` for persistence:
- Current song index
- Playing state (true/false)
- Loop mode (all/one/off)
- Volume level
- Last playback position
- First join flag

### Services Used
- `Players` - Player management
- `SoundService` - Audio playback
- `UserInputService` - Device detection
- `RunService` - Update loop for progress bar

### Sound Properties
- **Parent**: `SoundService` (survives character death)
- **Volume**: 0-2.5 (user input × 0.25)
- **Looped**: Dynamic based on loop mode

## 🐛 Troubleshooting

### Music stops after 1 second
- Check if audio IDs are valid
- Ensure audio is approved for Roblox
- Verify internet connection

### No auto-play on first join
- Check console for error messages
- Ensure script is in `StarterPlayerScripts`
- Verify `ResetOnSpawn = false` on ScreenGui

### Volume not working
- Input must be a number (0-10)
- Check if sound is muted in Roblox settings
- Verify `SoundService` is not muted

## 📝 Changelog

### Version 1.0.3 (Latest)
- ✨ Added auto-play on first join
- 🔧 Fixed music stopping after character spawn
- 🐛 Fixed sound playback issues with initialization timing
- 📊 Added detailed debug logging
- 🔄 Improved character respawn handling
- ⚡ Better sound loading verification

### Version 1.0.2
- 🔁 Added multiple loop modes (All, One, Off)
- 💾 Improved persistent storage system
- 📱 Enhanced mobile UI responsiveness
- 🎨 Better UI styling and animations

### Version 1.0.1
- 💾 Added save/load functionality
- 🐛 Bug fixes for playback state
- ⚡ Performance improvements

### Version 1.0.0 (Initial Release)
- 🎵 Basic music player functionality
- ⏯️ Play/pause controls
- ⏭️ Next/previous song navigation
- 🎚️ Volume control
- 📊 Progress bar

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues.

## 👤 Author

**ItoRenz00**

## 📄 License

This project is licensed under the MIT License.

## 🙏 Acknowledgments

- Roblox Developer Community
- All music artists featured in the playlist

---

**Made with ❤️ for the Roblox community**
