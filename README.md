# Peace Preset Generator

AI-powered EQ preset generator for [Peace Equalizer](https://sourceforge.net/projects/peace-equalizer-apo-extension/) (Equalizer APO extension). Uses headphone-specific profiles and audio engineering principles to generate optimized presets for any music genre.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## 🎧 What is This?

An **AI-powered preset generator** that creates genre-optimized EQ profiles for Peace Equalizer. Unlike generic device correction profiles, this tool generates **ready-to-import presets** that combine:

- **Headphone-specific compensation** - Corrects your model's frequency response weaknesses
- **Genre-specific optimization** - Different curves for Metal, Trance, Classical, etc.
- **Audio engineering expertise** - Professional EQ principles applied automatically

### What Makes This Different?

**✅ This project generates:**
- Genre-tailored presets (same headphones, different sound for different music)
- Ready-to-import `.peace` files (no manual configuration)
- AI-assisted creation at scale (request any genre + headphone combination)
- Detailed engineering rationale for each preset

**❌ This is NOT:**
- A manual device correction database
- A one-size-fits-all EQ profile
- A replacement for researching your headphone's characteristics
- Audio driver software or hardware modification

**Think of it as:** A smart preset factory that understands both your headphones' technical limitations AND what your favorite music genres need to shine.

## 🔍 Real-World Example

**Scenario:** You own Sennheiser HD 4.40 BT headphones and listen to both Heavy Metal and Classical music.

**Generic device profile approach:** One EQ curve that "corrects" your headphones. Sounds decent for everything, perfect for nothing.

**This generator's approach:** 
- `Heavy Metal - HD 4.40 BT.peace` - Aggressive, punchy, V-shaped curve
- `Classical - HD 4.40 BT.peace` - Natural, balanced, minimal coloration

Same headphones, different presets, optimized for each genre's specific needs.

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

See [`config/CREATED_PRESETS.md`](config/CREATED_PRESETS.md) for detailed descriptions and engineering notes.

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

1. Add your request to `config/PRESETS_TO_CREATE.md`:
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
2. Document in `config/CREATED_PRESETS.md` with reasoning
3. Submit a pull request

### Report Issues

Found a preset that sounds off? Open an issue with:
- Headphone model
- Genre preset used
- What sounds wrong
- Your music source quality

## 📖 Documentation

- [`CLAUDE.md`](CLAUDE.md) - Complete generation workflow and audio engineering principles
- [`config/CONFIG.md`](config/CONFIG.md) - Headphone configuration and defaults
- [`config/CREATED_PRESETS.md`](config/CREATED_PRESETS.md) - Detailed preset catalog with engineering notes
- [`headphone_profiles/`](headphone_profiles/) - Individual headphone analysis documents
- [`CONTRIBUTING.md`](CONTRIBUTING.md) - Contribution guidelines

## 🎯 Core Philosophy

### Genre + Headphone = Optimized Sound

This generator solves a specific problem: **Your headphones sound different depending on what you're listening to.**

A heavy metal track needs punchy, aggressive mids and controlled bass. A vocal trance track needs deep sub-bass and sparkling highs. Classical music needs natural balance with minimal coloration.

**Generic device profiles can't do this.** They correct the headphone but ignore the music.

This tool creates **targeted presets** that answer: *"How should these specific headphones be EQ'd for this specific genre?"*

### What You Get

Each generated preset includes:
- **Headphone analysis** - What frequencies need correction
- **Genre requirements** - What the music style demands
- **Engineering rationale** - Why each frequency band is adjusted
- **Ready-to-use file** - Just import and listen

### What You Need to Provide

- Your exact headphone model (or add it to the profiles)
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
- **Room acoustics matter**: Presets optimize headphones, not speakers
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
- Fixing hardware defects (get better headphones)
- Live audio processing (latency considerations)

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
