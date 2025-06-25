# Changelog

All notable changes to Auric Tamil Radio Bot will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-06-25

### Added
- 🎵 **Multi-station FM radio support** with 15+ Tamil stations
- 🎛️ **Interactive dropdown controls** for station selection
- ⏯️ **Playback controls** (play, pause, resume, stop)
- 🔄 **Auto-reconnection system** with retry limits and progressive delays
- 🏆 **Multi-server support** with per-guild state management
- 📱 **Smart message management** - single "Now Playing" message per server
- 🛡️ **Robust error handling** for all network and Discord operations
- 💾 **SQLite database** for persistent guild settings
- ⚡ **24/7 mode** for continuous playback
- 🎧 **Ultra-optimized FFmpeg settings** for minimal latency
- 📻 **Real-time voice connection monitoring**
- 🧹 **Automatic cleanup** of old messages and voice connections
- 🔊 **Enhanced audio quality** with bass boost and volume optimization
- 📋 **Comprehensive logging** for debugging and monitoring
- 🎮 **Slash command interface** with `/play`, `/stop`, `/list`, `/setup`, `/help`

### Technical Features
- **Memory leak prevention** with proper state cleanup
- **Progressive reconnection delays** to avoid server load
- **Voice drop recovery** with automatic stream restoration
- **Database error handling** with safe fallbacks
- **Interaction token expiry handling** for better user experience
- **FFmpeg optimization** for Discord Opus streaming
- **Concurrent server support** with isolated guild states

### Stations Included
1. MJOY - Vellore
2. தமிழர் வானொலி - Sempatti
3. Sona FM - Salem
4. Suryan FM 93.5
5. Covai FM 95.5
6. Hello FM 106.4
7. Radio Mirchi Tamil
8. SPB Hits HD
9. Radio City
10. Kodaikanal FM
11. Sad Songs Tamil
12. Tamil DJ Remix 24/7
13. Tamil Top 100
14. Tamil Hits 24/7
15. Netrikan-Tamil-HD

### Infrastructure
- Discord.py 2.3+ compatibility
- Python 3.8+ support
- Cross-platform FFmpeg integration
- Lightweight SQLite database
- Comprehensive error logging
- Production-ready stability

---

## Future Plans

### [1.1.0] - Planned
- [ ] Web dashboard for server management
- [ ] Custom station addition by server admins
- [ ] Playlist support and queue system
- [ ] Audio equalizer controls
- [ ] Statistics and usage analytics
- [ ] More regional Indian radio stations

### [1.2.0] - Planned
- [ ] Voice command support
- [ ] Integration with music streaming services
- [ ] Custom audio effects and filters
- [ ] Multi-language support (Telugu, Malayalam, Kannada)
- [ ] Mobile app companion

---

## Support

For support, bug reports, or feature requests:
- 🐛 [GitHub Issues](https://github.com/NirmaLKumar26/Auric-Tamil-FM-Radio/issues)
- 💬 [Discord Server](https://discord.gg/your-invite)
- 📧 Email: support@auricradio.com

---

*Made with ❤️ for the Tamil music community*
