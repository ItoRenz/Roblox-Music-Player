# 🎵 Roblox Music Player

A feature-rich, persistent music player for Roblox games with auto-save functionality and death/respawn handling.

![Roblox](https://img.shields.io/badge/Roblox-Studio-00a2ff?style=flat-square&logo=roblox)
![Lua](https://img.shields.io/badge/Lua-5.1-blue?style=flat-square&logo=lua)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

## ✨ Features

- 🎶 **40+ Pre-loaded Songs** - Curated playlist with popular tracks
- 💾 **Persistent Storage** - Automatically saves playback state across sessions
- 🔄 **Loop Modes** - Off, Loop All (default), Loop One
- 📱 **Mobile & Desktop Support** - Responsive UI for all devices
- 💀 **Death/Respawn Handling** - Resumes music after character respawn
- 🎚️ **Volume Control** - Adjustable volume (0-10)
- ⏯️ **Full Playback Controls** - Play, Pause, Next, Previous
- 📊 **Progress Bar** - Visual playback progress with time display
- 🎨 **Modern UI Design** - Sleek gradient design with smooth animations

## 📦 Installation

1. Open your Roblox game in **Roblox Studio**
2. In the Explorer, navigate to `StarterGui`
3. Create a new `ScreenGui` if you don't have one
4. Insert a `LocalScript` inside the `ScreenGui`
5. Copy and paste the code from `music-player.lua`
6. Save and test in-game!

```
StarterGui
└── ScreenGui
    └── LocalScript (paste code here)
```

## 🎮 Usage

### In-Game Controls

- **Music Button** - Click to toggle the music player UI
- **▶️/⏹️ Button** - Play/Stop the current track
- **⏮️ Button** - Previous track
- **⏭️ Button** - Next track
- **🔁 Button** - Cycle through loop modes (All → One → Off)
- **X Button** - Close the music player UI
- **Volume Input** - Enter a number between 0-10 to adjust volume

### Loop Modes

| Mode | Icon | Description |
|------|------|-------------|
| **Loop All** | 🔁 (Blue) | Automatically plays next song when current ends (Default) |
| **Loop One** | 🔂 (Orange) | Repeats the same song continuously |
| **Loop Off** | 🔁 (Gray) | Stops after song ends |

## 🎵 Playlist

The music player includes 40 tracks:
- Mantra Hujan
- Fond Memories
- Pandangan Pertama
- Koiiro
- Overdose
- Faded
- Alone
- And many more...

### Adding Your Own Songs

To add custom songs, edit the `musicList` table:

```lua
local musicList = {
    {id = "rbxassetid://YOUR_AUDIO_ID", title = "Song Title"},
    -- Add more songs here
}
```

## 💾 Data Persistence

The music player automatically saves:
- ✅ Current song index
- ✅ Playing state (playing/stopped)
- ✅ Loop mode preference
- ✅ Volume level
- ✅ Playback position

Data persists across:
- Server hops
- Character deaths/respawns
- Game rejoins (session-based)

## 🔧 Configuration

### Default Settings

```lua
local state = {
    currentIndex = 1,        -- First song
    isPlaying = false,       -- Stopped on load
    loopMode = "all",        -- Loop all songs
    volume = 2,              -- Volume level (0-10)
}
```

### Customization Options

| Setting | Location | Description |
|---------|----------|-------------|
| Mobile Detection | Line 16 | Adjust UI for mobile devices |
| UI Colors | Lines 132-149 | Change color scheme |
| UI Size | Lines 149-155 | Adjust player dimensions |
| Auto-save Interval | Line 454 | Change save frequency (default: 5 seconds) |

## 📱 Mobile vs Desktop

The script automatically detects the device type and adjusts:
- Button sizes
- Text sizes
- UI positioning
- Touch controls

## 🐛 Troubleshooting

### Music not playing?
- Check if audio IDs are valid and not moderated
- Verify volume is not set to 0
- Ensure sound service is not muted

### UI not showing?
- Verify the script is in `StarterGui > ScreenGui`
- Check `ResetOnSpawn` is set to `false`
- Click the "Music" toggle button

### Music stops after death?
- This is intentional if music was already stopped
- Music will auto-resume if it was playing before death

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Add new songs to the playlist
- Improve UI/UX design
- Fix bugs or optimize code
- Add new features

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👤 Author

Created for the Roblox development community

## 🌟 Acknowledgments

- Music tracks from various Roblox audio library
- Inspired by modern music player designs
- Built with Roblox Studio and Lua

---

⭐ If you find this useful, please consider starring the repository!

## 📞 Support

For issues, questions, or suggestions:
- Open an issue on GitHub
- Check existing issues for solutions
- Contribute via pull requests

---

**Note:** Make sure all audio assets are properly licensed and comply with Roblox's Terms of Service.
