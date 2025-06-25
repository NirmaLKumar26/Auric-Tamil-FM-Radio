# 🎙️ Auric Tamil Radio Bot

<div align="center">
  <img src="https://tndev.in/Auric.jpg" alt="Auric Tamil Radio" width="200"/>
  
  [![Discord](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)]([https://discord.gg/your-invite](https://discord.gg/etTMNChaVX))
  [![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
  [![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
  [![Stars](https://img.shields.io/github/stars/NirmaLKumar26/Auric-Tamil-FM-Radio?style=for-the-badge)](https://github.com/NirmaLKumar26/Auric-Tamil-FM-Radio)

  **Your South Indian FM Radio Companion — Bringing the sounds of home to Discord**
</div>

---

## 🌟 Features

<div align="center">
  
| 🎵 **Multi-Station Support** | 🔊 **High-Quality Audio** | 🔄 **Auto-Reconnection** |
|:---:|:---:|:---:|
| 15+ Tamil FM stations | Optimized FFmpeg streaming | Handles voice drops gracefully |

| 🎛️ **Interactive Controls** | 🏆 **Multi-Server** | ⚡ **24/7 Mode** |
|:---:|:---:|:---:|
| Dropdown menus & buttons | Works across multiple servers | Continuous playback support |

</div>

### 🎶 **Radio Stations**
- **MJOY Vellore** - Popular Tamil hits
- **Suryan FM 93.5** - Tamil entertainment 
- **Radio Mirchi Tamil** - Bollywood & Tamil mix
- **SPB Hits HD** - S.P. Balasubrahmanyam classics
- **Hello FM 106.4** - Contemporary music
- **Covai FM 95.5** - Local Coimbatore station
- **And 9 more stations!** 📻

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- FFmpeg installed on your system
- Discord Bot Token

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/NirmaLKumar26/Auric-Tamil-FM-Radio.git
   cd Auric-Tamil-FM-Radio
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure your bot**
   - Replace the bot token in `main.py` (line 837)
   - Update the admin user ID for `/247` command (line 354)

4. **Run the bot**
   ```bash
   python main.py
   ```

---

## 🎯 Usage

### Initial Setup
```bash
/setup
```
Creates a dedicated radio channel with interactive controls

### Basic Commands
| Command | Description | Example |
|---------|-------------|---------|
| `/play [id]` | Play a specific radio station | `/play 1` |
| `/list` | Show all available stations | `/list` |
| `/stop` | Stop radio and disconnect | `/stop` |
| `/help` | Show detailed help information | `/help` |

### Admin Commands
| Command | Description | Permission |
|---------|-------------|------------|
| `/247 [true/false]` | Enable/disable 24/7 mode | Admin only |

---

## 🎮 Interactive Features

### 🎛️ **Control Panel**
<div align="center">
  <img src="https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_1280.jpg" alt="Radio Interface" width="400"/>
</div>

- **Dropdown Station Selector** - Choose from 15+ stations
- **Pause/Resume Buttons** - Control playback
- **Stop Button** - Disconnect and cleanup
- **Real-time Updates** - Shows currently playing station

### 📱 **Smart Message Management**
- Automatic cleanup of old messages
- Single "Now Playing" message per server
- Protected setup channel messages

---

## 🔧 Technical Features

### 🎵 **Audio Optimization**
```python
# Ultra-optimized FFmpeg settings
before_options = "-reconnect 1 -reconnect_streamed 1 -reconnect_delay_max 2 -reconnect_at_eof 1 -loglevel fatal -nostdin -thread_queue_size 2048 -rtbufsize 64M -probesize 32768 -analyzeduration 0"

options = "-vn -acodec libopus -b:a 128k -bufsize 4096k -maxrate 128k -minrate 96k -fflags +discardcorrupt -flags +global_header -af aresample=48000,volume=0.8,dynaudnorm=f=100:g=15:p=0.9:m=10:r=0.1:n=1"
```

### 🛡️ **Reliability Features**
- **Auto-reconnection** with retry limits and progressive delays
- **Voice connection monitoring** every 60 seconds
- **Error handling** for all network and Discord API operations
- **Database persistence** for guild settings and channel states
- **Memory leak prevention** with proper cleanup

### 🏗️ **Architecture**
- **Per-guild state management** - Isolated server configurations
- **SQLite database** - Lightweight local storage
- **Async/await patterns** - Non-blocking operations
- **Modular design** - Easy to extend and maintain

---

## 📋 Requirements

```txt
discord.py>=2.3.0
asyncio
sqlite3
logging
```

### System Requirements
- **FFmpeg** - For audio processing
- **Python 3.8+** - Core runtime
- **2GB RAM** - Recommended for multiple servers
- **Stable internet** - For radio stream reliability

---

## 🎨 Customization

### Adding New Stations
```python
radio_stations = [
    {
        "id": 16,
        "name": "Your Station Name",
        "url": "https://your-stream-url.com/stream.mp3",
        "image": "https://your-image-url.com/logo.jpg"
    }
]
```

### Modifying Audio Settings
Adjust FFmpeg parameters in the `create_optimized_audio_source()` function:
- **Bitrate**: `-b:a 128k`
- **Volume**: `volume=0.8`
- **Buffer size**: `-bufsize 4096k`

---

## 🐛 Troubleshooting

### Common Issues

#### **FFmpeg not found**
```bash
# Windows (using Chocolatey)
choco install ffmpeg

# Ubuntu/Debian
sudo apt update && sudo apt install ffmpeg

# MacOS (using Homebrew)
brew install ffmpeg
```

#### **Voice connection issues**
- Ensure bot has "Connect" and "Speak" permissions in voice channels
- Check if bot is already connected to another channel
- Verify FFmpeg is properly installed

#### **Database errors**
- Check file permissions for `radio_data.db`
- Ensure SQLite3 is available in your Python installation

### Debug Mode
Enable detailed logging by changing the log level:
```python
logging.basicConfig(level=logging.DEBUG)
```

---

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines
- Follow PEP 8 style guidelines
- Add proper error handling
- Include logging for debugging
- Test with multiple Discord servers
- Document any new features

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Discord.py** - Amazing Python Discord library
- **FFmpeg** - Powerful multimedia framework
- **Radio stations** - Thanks to all the radio providers
- **Tamil music community** - For keeping the culture alive

---

## 📞 Support

<div align="center">

### Need Help?

[![Discord Server](https://img.shields.io/badge/Join%20Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)]([https://discord.gg/your-invite](https://discord.gg/etTMNChaVX))
[![GitHub Issues](https://img.shields.io/badge/GitHub%20Issues-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/NirmaLKumar26/Auric-Tamil-FM-Radio/issues)

**Found a bug?** [Report it here](https://github.com/NirmaLKumar26/Auric-Tamil-FM-Radio/issues/new)

**Have a suggestion?** [Share your ideas](https://github.com/NirmaLKumar26/Auric-Tamil-FM-Radio/discussions)

</div>

---

<div align="center">

### 🎵 Bringing Tamil Music to Discord Servers Worldwide 🎵

**Made with ❤️ for the Tamil music community**

*Star ⭐ this repository if you found it helpful!*

</div>
