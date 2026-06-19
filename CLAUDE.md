# Peace Equalizer Preset Generator

This repository generates **genre-specific** Peace Equalizer presets optimized for individual audio devices (headphones, speakers, soundbars, etc).

## Key Distinction

**This is NOT a device correction database.** This generates genre-optimized presets that combine:
1. Device-specific frequency response compensation
2. Genre-appropriate EQ curves (Metal ≠ Classical ≠ Trance)
3. Professional audio engineering principles
4. Use-case considerations (near-field headphones vs room-filling speakers)

**Output:** Ready-to-import `.peace` files, not manual frequency specifications.

**Default Target:** Check `config/CONFIG.md` for the currently active device profile.  
**Available Profiles:** See `device_profiles/` directory organized by device type.

## Workflow

1. User adds music styles to `config/PRESETS_TO_CREATE.md`
   - Format: `[Style] @ [Device Model]` (or omit model to use default from config/CONFIG.md)
2. User says "create the presets" or "run it"
3. Claude:
   - Reads `config/CONFIG.md` for the active/default device
   - Reads the spec file
   - For each preset, determines which device profile to use
   - Reads the appropriate profile from `device_profiles/[category]/[Model].md`
   - Generates `.peace` files in `output/` folder with format: `[Style] - [Model].peace`
   - Adds to `config/CREATED_PRESETS.md` with date, description, and target device
   - Clears completed items from spec file

## Preset Format

Peace Equalizer presets use an INI-style format:

```
[Frequencies]
Frequency1=10
Frequency2=21
Frequency3=42
Frequency4=83
Frequency5=166
Frequency6=333
Frequency7=577
Frequency8=1000
Frequency9=2000
Frequency10=4000
Frequency11=8000
Frequency12=16000
Frequency13=20000

[Gains]
Gain1=<value>    # dB adjustment for 10 Hz
Gain2=<value>    # dB adjustment for 21 Hz
...
Gain13=<value>   # dB adjustment for 20000 Hz

[Qualities]
Quality1=0.7
Quality2=0.7
...
Quality13=0.7
```

### Fixed Parameters
- **Frequencies**: Always the same 13 bands (10 Hz to 20 kHz)
- **Quality factors**: Typically 0.7 for all bands
- **File extension**: `.peace`

### Variable Parameters
- **Gains**: Range from -12 to +12 dB (typical: -6 to +8 dB)

## Frequency Band Characteristics

| Band | Frequency | Characteristics |
|------|-----------|-----------------|
| 1-2 | 10-21 Hz | Sub-bass, felt more than heard |
| 3-4 | 42-83 Hz | Bass fundamentals, warmth |
| 5-6 | 166-333 Hz | Upper bass, body |
| 7 | 577 Hz | Lower midrange, muddiness zone |
| 8-9 | 1000-2000 Hz | Midrange, vocal presence |
| 10-11 | 4000-8000 Hz | Upper midrange, clarity, sibilance |
| 12-13 | 16000-20000 Hz | Air, sparkle, brilliance |

## Genre-Specific EQ Guidelines

### Rock/Metal
- Boost: Sub-bass (10-42 Hz), upper mids (4-8 kHz)
- Cut: Lower mids (300-600 Hz) to reduce muddiness
- V-shaped for aggression

### Electronic/EDM
- Strong boost: Sub-bass (10-83 Hz)
- Moderate boost: Upper treble (8-20 kHz)
- Deep V-shaped curve

### Classical/Orchestral
- Gentle, natural curve
- Slight boost: Upper treble for air
- Minimal bass boost

### Jazz/Blues
- Warm, smooth curve
- Boost: Mid-bass (83-333 Hz)
- Gentle high roll-off

### Pop/R&B
- Balanced with slight V-shape
- Clear vocals in midrange
- Enhanced bass and highs

### Hip-Hop/Trap
- Heavy sub-bass (10-83 Hz)
- Controlled mids
- Clear highs for hi-hats and details

### Ambient/Chill
- Warm, smooth curve
- Gentle bass presence
- Soft, rolled-off highs

## File Organization

Save all generated presets to `/output` folder:
- Path: `output/[Style Name] - [Device Model].peace`
- Format: Always include the device model in the filename
- Examples: 
  - `output/Heavy Metal - HD 4.40 BT.peace`
  - `output/Vocal Trance - JBL Flip 6.peace`
  - `output/Classical - Sony WH-1000XM5.peace`

After generating presets, update `CREATED_PRESETS.md` with:
- Date of creation
- Preset name (including device model)
- Target device type (headphone/speaker/etc)
- Brief description of EQ characteristics

## Preset Generation Philosophy

**IMPORTANT:** Presets are generated using **audio engineering expertise**, not by copying user samples or generic device profiles.

### What Makes These Presets Unique

Unlike generic device correction profiles that provide one-size-fits-all EQ:
- **These are genre-specific** - Heavy Metal gets a different curve than Classical
- **These combine two analyses** - Headphone weaknesses + Genre requirements
- **These are ready-to-use** - Output is importable `.peace` files, not manual specs

### Generation Process
1. **Analyze the device** - Read its profile to understand frequency response, strengths, weaknesses, and use case
2. **Analyze the genre** - Understand what frequencies and balance the music style requires
3. **Consider the environment** - Headphones vs speakers require different approaches (room acoustics, listening distance)
4. **Design the EQ curve** - Apply professional audio engineering principles to:
   - Compensate for device deficiencies
   - Enhance genre-appropriate frequencies  
   - Balance technical accuracy with musical enjoyment
5. **Generate confidently** - Use proven EQ knowledge to create optimal presets

### Why This Matters

A "Vocal Trance" preset for **Sennheiser HD 4.40 BT** (headphone) will:
- Boost sub-bass (genre requirement) BUT limit mid-bass (headphone already bass-heavy)
- Scoop lower mids (genre requirement) AND avoid the HD 4.40 BT's muddy zone
- Boost treble (genre requirement) AND compensate for Bluetooth roll-off

The same preset for **JBL Flip 6** (portable speaker) will:
- Control mid-bass boom (speaker's weakness) MORE aggressively than headphones
- Account for room boundary reinforcement (wall proximity adds bass)
- Compensate for listening distance (speakers sound different at 1m vs 3m)
- Respect physical limits (small speaker can't reproduce deep sub-bass)

This is **impossible with generic profiles** that don't know what music you're playing or how you're listening.

### Engineering Principles
- **Sub-bass (10-42 Hz)**: Impact and rumble for electronic/bass-heavy genres
- **Mid-bass (83-166 Hz)**: Warmth and body, but prone to boom - cut when needed
- **Lower mids (333-577 Hz)**: Muddiness zone - often needs cutting for clarity
- **Midrange (1-2 kHz)**: Vocal presence - boost for forward vocals, cut for atmospheric sound
- **Upper mids (4-8 kHz)**: Clarity and definition - careful with sibilance
- **Treble (8-20 kHz)**: Air and sparkle - boost to compensate for Bluetooth roll-off

### Device-Specific Adjustments

**Headphones:**
- **Bass-heavy headphones** (JBL): Cut mid-bass more aggressively, boost treble more
- **Balanced headphones** (Sennheiser): Moderate adjustments
- **Bright headphones**: Less treble boost, more careful with 4-8 kHz
- **Bluetooth models**: Always compensate for high-frequency roll-off

**Speakers:**
- **Portable speakers** (JBL Flip): Control mid-bass boom, respect sub-bass limits, account for room acoustics
- **Desktop monitors**: Nearfield listening, accurate midrange, controlled bass
- **Soundbars**: TV audio compensation, dialog clarity, virtual surround considerations
- **Home theater**: Multi-channel routing (future), subwoofer crossovers, room correction

## Adding New Device Profiles

To add support for a new device:

1. Research the device's frequency response and sound signature
2. Determine device category (headphone, portable speaker, desktop speaker, soundbar, home theater)
3. Create `device_profiles/[category]/[Model Name].md` using existing profiles as template
4. Include:
   - Device type and channel configuration (2.0, 2.1, 5.1, 7.1)
   - Native sound signature (bass/mid/treble characteristics)
   - Connection type (wired/Bluetooth/USB/optical)
   - Use case considerations (listening distance, room placement, volume levels)
   - Known strengths and weaknesses
   - Compensation strategy with frequency-specific guidelines
   - Technical specifications
   - Physical limitations and warnings
5. Add to `CONFIG.md` available profiles list
6. Optionally update default target in `CONFIG.md`

## Future Development

See `ROADMAP.md` for planned features:
- **Phase 2:** Filter support (HPF, LPF, shelving, notch filters) via EqualizerAPO `.txt` format
- **Phase 3:** Multi-channel support (5.1, 7.1 surround systems)
- Additional device categories (IEMs, studio monitors, car audio, gaming headsets)
