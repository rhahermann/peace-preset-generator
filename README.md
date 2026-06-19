# Peace Preset Generator

AI-powered EQ preset generator for [Peace Equalizer](https://sourceforge.net/projects/peace-equalizer-apo-extension/) (Equalizer APO extension). Uses device-specific profiles and audio engineering principles to generate optimized presets for any audio device and music genre.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## 🎧 What is This?

An **AI-powered preset generator** that creates genre-optimized EQ profiles for Peace Equalizer. Unlike generic device correction profiles, this tool generates **ready-to-import presets** that combine:

- **Device-specific compensation** - Corrects your headphones/speakers frequency response weaknesses
- **Genre-specific optimization** - Different curves for Metal, Trance, Classical, etc.
- **Audio engineering expertise** - Professional EQ principles applied automatically

### What Makes This Different?

**✅ This project generates:**
- Genre-tailored presets (same device, different sound for different music)
- Ready-to-import `.peace` files (no manual configuration)
- AI-assisted creation at scale (request any genre + device combination)
- Detailed engineering rationale for each preset

**❌ This is NOT:**
- A manual device correction database
- A one-size-fits-all EQ profile
- A replacement for researching your device's characteristics
- Audio driver software or hardware modification

**Think of it as:** A smart preset factory that understands both your audio device's technical limitations AND what your favorite music genres need to shine.

## 🔍 Real-World Example

**Scenario:** You own Sennheiser HD 4.40 BT headphones and a JBL Flip 6 speaker. You listen to both Heavy Metal and Classical music.

**Generic device profile approach:** One EQ curve that "corrects" your device. Sounds decent for everything, perfect for nothing.

**This generator's approach:** 
- `Heavy Metal - HD 4.40 BT.peace` - Aggressive headphone curve (closed-back, sealed bass)
- `Heavy Metal - JBL Flip 6.peace` - Controlled speaker curve (room acoustics, distance-aware)
- `Classical - HD 4.40 BT.peace` - Natural headphone balance
- `Classical - JBL Flip 6.peace` - Natural speaker balance (different from headphone version)

Same genres, different devices, each preset optimized for the specific combination.

## 🚀 Quick Start

### Prerequisites

1. **Install Peace Equalizer**
   - Download and install [Equalizer APO](https://sourceforge.net/projects/equalizerapo/)
   - Download and install [Peace](https://sourceforge.net/projects/peace-equalizer-apo-extension/)

### Using Existing Presets

1. Browse the `output/` folder for available presets
2. Download a `.peace` file that matches your audio device (headphones or speakers)
3. Open Peace Equalizer
4. Click "Import" and select the downloaded preset
5. Enjoy optimized audio!

## 📦 Available Presets

Currently available for:

### Headphones
**Sennheiser HD 4.40 BT**
- ✅ Vocal Trance
- ✅ Heavy Metal
- ✅ Melodic Metal

**JBL Tune 520BT**
- ✅ Vocal Trance
- ✅ Heavy Metal
- ✅ Melodic Metal

### Speakers
**JBL Flip 6 (Portable)**
- ✅ Metal
- ✅ Hard Rock

See [`config/CREATED_PRESETS.md`](config/CREATED_PRESETS.md) for detailed descriptions and engineering notes.

## 🎛️ How It Works

### 1. Device Profiles
Each supported device has a detailed profile documenting:
- Native frequency response characteristics
- Known strengths and weaknesses
- Compensation strategies
- Device type (headphone/speaker/soundbar)
- Connection type (Bluetooth/wired/optical)
- Use case considerations (listening distance, room placement)

See [`device_profiles/`](device_profiles/) for examples.

### 2. Genre Analysis
The generator understands what different music genres need:
- **Electronic/Trance**: Deep sub-bass, scooped mids, sparkly highs
- **Metal**: Punchy bass, clear mids (no mud), aggressive treble
- **Pop/R&B**: Balanced with vocal presence
- **Classical**: Natural, minimal correction

### 3. AI-Assisted Generation
Using audio engineering principles, the generator:
1. Reads the device profile
2. Analyzes genre requirements
3. Accounts for device type and use case (headphones vs speakers)
4. Calculates optimal EQ compensation
5. Generates the `.peace` preset file

## 🔧 Generating New Presets

Want a preset for a different genre or your specific audio device?

### Option 1: Request via Issue
Open a [GitHub Issue](https://github.com/rhahermann/peace-preset-generator/issues) with:
- Your device model (headphone, speaker, soundbar)
- Desired music genre
- Any specific preferences

### Option 2: Use Claude Code (AI-Assisted)
If you have access to Claude Code:

1. Add your request to `config/PRESETS_TO_CREATE.md`:
   ```
   Lo-Fi Hip-Hop @ Sennheiser HD 4.40 BT
   Progressive House @ JBL Flip 6
   Classical @ Default
   ```

2. Run the generator workflow (see [`CLAUDE.md`](CLAUDE.md))

3. New presets appear in `output/` with engineering notes

## 🎯 Supported Devices

### Headphones
- ✅ **Sennheiser HD 4.40 BT** - Bluetooth, V-shaped signature
- ✅ **JBL Tune 520BT** - Bluetooth, bass-heavy consumer tuning

### Speakers
- ✅ **JBL Flip 6** - Portable Bluetooth speaker, 2.0 stereo

Want to add your device? See [Contributing](#-contributing) below.

## 📊 Preset Format

Each `.peace` file uses 13 frequency bands:

| Frequency | Purpose |
|-----------|---------|
| 10-21 Hz | Sub-bass (felt impact) |
| 42-83 Hz | Bass fundamentals |
| 166-333 Hz | Upper bass / muddiness zone |
| 577 Hz | Lower mids (clarity) |
| 1-2 kHz | Midrange (vocal presence) |
| 4-8 kHz | Upper mids (definition) |
| 16-20 kHz | Treble (air and sparkle) |

Gain adjustments: `-12 dB` to `+12 dB`  
Quality factor: `0.7` (standard)

## 🤝 Contributing

Contributions welcome! Here's how:

### Add Your Device Profile

1. Fork this repository
2. Research your device's frequency response (RTINGS, Crinacle, ASR, manufacturer specs)
3. Create `device_profiles/[category]/[Your Model].md` using existing profiles as template
4. Add to `CONFIG.md` available profiles list
5. Submit a pull request

### Share Your Preset

If you've manually tuned a great preset:
1. Add it to `output/[Genre] - [Device].peace`
2. Document in `config/CREATED_PRESETS.md` with reasoning
3. Submit a pull request

### Report Issues

Found a preset that sounds off? Open an issue with:
- Device model (headphone/speaker/etc)
- Genre preset used
- What sounds wrong
- Your music source quality

## 📖 Documentation

- [`CLAUDE.md`](CLAUDE.md) - Complete generation workflow and audio engineering principles
- [`config/CONFIG.md`](config/CONFIG.md) - Device configuration and defaults
- [`config/CREATED_PRESETS.md`](config/CREATED_PRESETS.md) - Detailed preset catalog with engineering notes
- [`device_profiles/`](device_profiles/) - Individual device analysis documents (headphones, speakers, etc)
- [`ROADMAP.md`](ROADMAP.md) - Future development plans (filters, multi-channel support)
- [`CONTRIBUTING.md`](CONTRIBUTING.md) - Contribution guidelines

## 🎯 Core Philosophy

### Genre + Device = Optimized Sound

This generator solves a specific problem: **Your audio device sounds different depending on what you're listening to.**

A heavy metal track needs punchy, aggressive mids and controlled bass. A vocal trance track needs deep sub-bass and sparkling highs. Classical music needs natural balance with minimal coloration.

**Generic device profiles can't do this.** They correct the device but ignore the music and use case.

This tool creates **targeted presets** that answer: *"How should this specific device (headphones/speakers) be EQ'd for this specific genre?"*

### What You Get

Each generated preset includes:
- **Device analysis** - What frequencies need correction
- **Genre requirements** - What the music style demands
- **Use case considerations** - Room acoustics, listening distance (for speakers)
- **Engineering rationale** - Why each frequency band is adjusted
- **Ready-to-use file** - Just import and listen

### What You Need to Provide

- Your exact device model (or add it to the profiles)
- The music genre you want optimized
- Trust in audio engineering principles (or tweak to taste)

## 🔬 Technical Details

### Why These Specific Frequencies?

The 13-band configuration covers the entire audible spectrum with focus on:
- **Sub-bass extension** (10-21 Hz) - Physical impact
- **Bass control** (42-166 Hz) - Warmth without boom
- **Mid clarity** (333-577 Hz) - Reducing muddiness
- **Vocal presence** (1-2 kHz) - Forward vs atmospheric
- **Definition** (4-8 kHz) - Clarity without sibilance
- **Air** (16-20 kHz) - Sparkle and space

### Bluetooth Compensation

Bluetooth presets account for:
- High-frequency roll-off (codec limitations)
- Dynamic compression
- Latency (not audible in EQ but documented)

## ⚠️ Important Notes

- **Start conservative**: Try presets at 80% volume first
- **Room acoustics matter for speakers**: Speaker presets assume typical room placement; adjust if near walls
- **Headphones vs Speakers**: Don't use headphone presets on speakers (or vice versa) - each is optimized differently
- **Source quality**: High-quality audio files benefit most from EQ
- **Personal preference**: Feel free to adjust +/- 2dB to taste
- **Hearing safety**: Avoid excessive bass boost at high volumes
- **Genre-specific**: A "Heavy Metal" preset will sound wrong on classical music (that's the point!)
- **Not a fix-all**: Can't fix broken drivers or poor source material

## 💡 Use Cases

**Perfect for:**
- Music enthusiasts who listen to multiple genres
- Audiophiles wanting optimized sound per music style
- Users tired of manually tweaking EQ for different playlists
- Anyone wanting professional-grade presets without the learning curve

**Not ideal for:**
- All-purpose "set and forget" EQ (use generic device profiles instead)
- Professional mixing/mastering (use flat reference monitoring)
- Fixing hardware defects (get better equipment)
- Live audio processing (latency considerations)
- Multi-channel surround systems (not yet supported - see ROADMAP.md)

## 📜 License

GNU General Public License v3.0 - See [LICENSE](LICENSE) for details.

This project is independent and not affiliated with Peace Equalizer or Equalizer APO.

## 🙏 Credits

- **Peace Equalizer** by [Peter Verbeek](https://sourceforge.net/u/peter_v/profile/)
- **Equalizer APO** for the audio processing engine
- Audio engineering principles from the professional audio community
- AI assistance via Claude Code for preset generation

## 🔗 Links

- [Peace Equalizer](https://sourceforge.net/projects/peace-equalizer-apo-extension/)
- [Equalizer APO](https://sourceforge.net/projects/equalizerapo/)
- [Report Issues](https://github.com/rhahermann/peace-preset-generator/issues)

---

**Made with 🎵 using audio engineering expertise and AI assistance**
