# Peace Preset Generator

AI-powered EQ preset generator for [Peace Equalizer](https://sourceforge.net/projects/peace-equalizer-apo-extension/) (Equalizer APO extension). Uses headphone-specific profiles and audio engineering principles to generate optimized presets for any music genre.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🎧 What is This?

A systematic approach to creating high-quality EQ presets that compensate for specific headphone characteristics while optimizing for different music genres. Instead of manually tuning EQ curves, this generator uses audio engineering knowledge to create presets tailored to:

- **Your specific headphones** (frequency response compensation)
- **Your music genre** (genre-appropriate EQ curves)
- **Professional audio principles** (optimal frequency balance)

## 🚀 Quick Start

### Prerequisites

1. **Install Peace Equalizer**
   - Download and install [Equalizer APO](https://sourceforge.net/projects/equalizerapo/)
   - Download and install [Peace](https://sourceforge.net/projects/peace-equalizer-apo-extension/)

### Using Existing Presets

1. Browse the `output/` folder for available presets
2. Download a `.peace` file that matches your headphones
3. Open Peace Equalizer
4. Click "Import" and select the downloaded preset
5. Enjoy optimized audio!

## 📦 Available Presets

Currently available for:

### Sennheiser HD 4.40 BT
- ✅ Vocal Trance
- ✅ Heavy Metal
- ✅ Melodic Metal

### JBL Tune 520BT
- ✅ Vocal Trance
- ✅ Heavy Metal
- ✅ Melodic Metal

See [`CREATED_PRESETS.md`](CREATED_PRESETS.md) for detailed descriptions and engineering notes.

## 🎛️ How It Works

### 1. Headphone Profiles
Each supported headphone has a detailed profile documenting:
- Native frequency response characteristics
- Known strengths and weaknesses
- Compensation strategies
- Connection type (Bluetooth/wired considerations)

See [`headphone_profiles/`](headphone_profiles/) for examples.

### 2. Genre Analysis
The generator understands what different music genres need:
- **Electronic/Trance**: Deep sub-bass, scooped mids, sparkly highs
- **Metal**: Punchy bass, clear mids (no mud), aggressive treble
- **Pop/R&B**: Balanced with vocal presence
- **Classical**: Natural, minimal correction

### 3. AI-Assisted Generation
Using audio engineering principles, the generator:
1. Reads the headphone profile
2. Analyzes genre requirements
3. Calculates optimal EQ compensation
4. Generates the `.peace` preset file

## 🔧 Generating New Presets

Want a preset for a different genre or your specific headphones?

### Option 1: Request via Issue
Open a [GitHub Issue](https://github.com/rhahermann/peace-preset-generator/issues) with:
- Your headphone model
- Desired music genre
- Any specific preferences

### Option 2: Use Claude Code (AI-Assisted)
If you have access to Claude Code:

1. Add your request to `PRESETS_TO_CREATE.md`:
   ```
   Lo-Fi Hip-Hop @ Sennheiser HD 4.40 BT
   Progressive House @ JBL Tune 520BT
   ```

2. Run the generator workflow (see [`CLAUDE.md`](CLAUDE.md))

3. New presets appear in `output/` with engineering notes

## 🎯 Supported Headphones

- ✅ **Sennheiser HD 4.40 BT** - Bluetooth, V-shaped signature
- ✅ **JBL Tune 520BT** - Bluetooth, bass-heavy consumer tuning

Want to add your headphones? See [Contributing](#-contributing) below.

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

### Add Your Headphone Profile

1. Fork this repository
2. Research your headphone's frequency response (RTINGS, Crinacle, ASR, etc.)
3. Create `headphone_profiles/[Your Model].md` using existing profiles as template
4. Add to `CONFIG.md` available profiles list
5. Submit a pull request

### Share Your Preset

If you've manually tuned a great preset:
1. Add it to `output/[Genre] - [Headphone].peace`
2. Document in `CREATED_PRESETS.md` with reasoning
3. Submit a pull request

### Report Issues

Found a preset that sounds off? Open an issue with:
- Headphone model
- Genre preset used
- What sounds wrong
- Your music source quality

## 📖 Documentation

- [`CLAUDE.md`](CLAUDE.md) - Complete generation workflow and audio engineering principles
- [`CONFIG.md`](CONFIG.md) - Headphone configuration and defaults
- [`CREATED_PRESETS.md`](CREATED_PRESETS.md) - Detailed preset catalog with engineering notes
- [`headphone_profiles/`](headphone_profiles/) - Individual headphone analysis documents

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
- **Room acoustics matter**: Presets optimize headphones, not speakers
- **Source quality**: High-quality audio files benefit most from EQ
- **Personal preference**: Feel free to adjust +/- 2dB to taste
- **Hearing safety**: Avoid excessive bass boost at high volumes

## 📜 License

MIT License - See [LICENSE](LICENSE) for details.

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
