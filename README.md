# 🎵 Roblox Music Player

**Author:** ItoRenz00  
**Version:** 1.0.0  
**License:** MIT

An advanced, feature-rich music player for Roblox with persistent state management, multiple loop modes, and full mobile support.

---

## ✨ Features

- 🎼 **40+ Built-in Songs** - Curated playlist with various genres
- 💾 **Persistent State** - Remembers your playback state across sessions
- 🔄 **Three Loop Modes** - Off, Loop All, Loop One
- 📱 **Mobile Optimized** - Responsive UI for both PC and mobile devices
- 🎚️ **Volume Control** - Adjustable volume from 0-10
- ⏯️ **Full Playback Controls** - Play, pause, next, previous
- 📊 **Progress Bar** - Visual representation of playback progress
- 🔊 **Time Display** - Current time and total duration
- 💀 **Death Persistence** - Resumes music after respawn
- 🎨 **Modern UI** - Clean, gradient-based design with smooth animations

---

## 📦 Installation

1. **Open Roblox Studio**
2. **Navigate to:** `StarterGui` in the Explorer panel
3. **Create a ScreenGui:**
   - Right-click `StarterGui`
   - Select `Insert Object` → `ScreenGui`
4. **Add the Script:**
   - Right-click the newly created `ScreenGui`
   - Select `Insert Object` → `LocalScript`
   - Paste the music player code into the script
5. **Configure Settings (Optional):**
   - Modify the `musicList` table to add your own songs
   - Adjust default volume in the `state` table
6. **Test the Game** to ensure everything works

---

## 🎮 Usage

### Controls

| Button | Function |
|--------|----------|
| **MUSIC** | Toggle music player UI visibility |
| **▶️ / ⏹️** | Play / Stop current song |
| **⏮️** | Previous song |
| **⏭️** | Next song |
| **🔁 / 🔂** | Cycle through loop modes (Off → All → One) |
| **Volume Input** | Set volume (0-10) |
| **X** | Close music player UI |

### Loop Modes

- **Loop: Off** 🔁 (Gray) - Stops after current song ends
- **Loop: All** 🔁 (Blue) - Automatically plays next song in playlist
- **Loop: One** 🔂 (Orange) - Repeats current song indefinitely

### First Time Setup

On first join, the music player will automatically start playing with "Loop: All" mode enabled.

---

## 🛠️ Customization

### Adding Your Own Songs

Modify the `musicList` table in the script:

```lua
local musicList = {
    {id = "rbxassetid://YOUR_AUDIO_ID", title = "Your Song Title"},
    {id = "rbxassetid://YOUR_AUDIO_ID", title = "Another Song"},
    -- Add more songs here
}
```

### Changing Default Settings

Edit the `state` table:

```lua
local state = {
    currentIndex = 1,      -- Starting song index
    isPlaying = false,     -- Auto-play on join
    loopMode = "all",      -- Default loop mode: "off", "all", or "one"
    volume = 2,            -- Default volume (0-10)
}
```

### UI Positioning

Adjust button positions in the UI setup section:

```lua
-- For PC
Position = UDim2.new(0.5, -190, 0, 12)

-- For Mobile
Position = UDim2.new(0.5, -15, 0, 12)
```

---

## 🔧 Technical Details

### Architecture

- **Service-Based**: Uses Roblox services (Players, SoundService, UserInputService, RunService)
- **State Management**: Centralized state object with persistent storage via `_G`
- **Event-Driven**: Connects to player events for seamless experience
- **Mobile Detection**: Automatically detects device type and adjusts UI

### Persistent Storage

The player saves the following data:
- Current song index
- Playing/stopped state
- Loop mode preference
- Volume level
- Playback time position

Data is stored in `_G.MusicPlayerData` and persists across:
- Character respawns
- Server hops (in same session)
- UI toggles

### Performance Optimizations

- **Heartbeat-based updates**: Smooth progress bar animation
- **Auto-save interval**: Saves state every 5 seconds during playback
- **Efficient rendering**: Mobile-optimized UI elements
- **Error handling**: Graceful failure with automatic song skip

---

## 📋 Requirements

- Roblox Studio (any recent version)
- LocalScript execution environment
- Audio assets uploaded to Roblox

---

## 🐛 Troubleshooting

### Music Won't Play

1. **Check Audio IDs**: Ensure all `rbxassetid://` URLs are valid
2. **Verify Permissions**: Make sure audio assets are public or you own them
3. **Console Errors**: Check Output window for error messages

### UI Not Showing

1. **Script Location**: Confirm script is in `StarterGui > ScreenGui`
2. **ResetOnSpawn**: Ensure ScreenGui's `ResetOnSpawn` is set to `false`
3. **Click MUSIC Button**: The UI is hidden by default

### Music Stops After Death

This is intentional behavior if music wasn't playing before death. The player preserves your playback state.

### Volume Too Loud/Quiet

- Adjust volume using the input box (0-10 range)
- Internal multiplier: `actualVolume = inputValue * 0.25`
- Maximum Roblox volume is 10, but player caps at 2.5 actual volume

---

## 📝 Version History

### v1.0.0 (Current)
- ✅ Initial release
- ✅ 40+ songs included
- ✅ Persistent state management
- ✅ Three loop modes
- ✅ Mobile support
- ✅ Death/respawn persistence
- ✅ Volume control
- ✅ Progress bar with time display

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Suggested Improvements

- [ ] Playlist management UI
- [ ] Shuffle mode
- [ ] Search/filter functionality
- [ ] Custom keybinds
- [ ] Visual equalizer
- [ ] Song favorites system
- [ ] Export/import playlists

---

## 📄 License

This project is licensed under the MIT License - see below for details:

```
MIT License

Copyright (c) 2025 ItoRenz00

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📞 Contact & Support

- **Author:** ItoRenz00
- **Issues:** Please report bugs via GitHub Issues
- **Suggestions:** Feature requests are welcome!

---

## ⭐ Acknowledgments

- Thanks to the Roblox developer community
- All music artists whose songs are featured
- Beta testers and contributors

---

**Enjoy your music! 🎶**
