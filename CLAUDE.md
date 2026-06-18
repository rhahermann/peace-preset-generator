# Peace Equalizer Preset Generator

This repository generates custom Peace Equalizer presets based on music genres and listening styles, optimized for specific headphone models.

**Default Target:** Check `config/CONFIG.md` for the currently active headphone profile.  
**Available Profiles:** See `headphone_profiles/` directory.

## Workflow

1. User adds music styles to `config/PRESETS_TO_CREATE.md`
   - Format: `[Style] @ [Headphone Model]` (or omit model to use default from config/CONFIG.md)
2. User says "create the presets" or "run it"
3. Claude:
   - Reads `config/CONFIG.md` for the active/default headphone
   - Reads the spec file
   - For each preset, determines which headphone profile to use
   - Reads the appropriate profile from `headphone_profiles/[Model].md`
   - Generates `.peace` files in `output/` folder with format: `[Style] - [Model].peace`
   - Adds to `config/CREATED_PRESETS.md` with date, description, and target headphone
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
- Path: `output/[Style Name] - [Headphone Model].peace`
- Format: Always include the headphone model in the filename
- Examples: 
  - `output/Heavy Metal - HD 4.40 BT.peace`
  - `output/Vocal Trance - Sony WH-1000XM5.peace`

After generating presets, update `CREATED_PRESETS.md` with:
- Date of creation
- Preset name (including headphone model)
- Target headphone
- Brief description of EQ characteristics

## Preset Generation Philosophy

**IMPORTANT:** Presets are generated using **audio engineering expertise**, not by copying user samples.

### Process
1. **Analyze the headphone** - Read its profile to understand frequency response characteristics, strengths, and weaknesses
2. **Analyze the genre** - Understand what frequencies and balance the music style requires
3. **Design the EQ curve** - Apply professional audio engineering principles to:
   - Compensate for headphone deficiencies
   - Enhance genre-appropriate frequencies  
   - Balance technical accuracy with musical enjoyment
4. **Generate confidently** - Use proven EQ knowledge to create optimal presets

### Engineering Principles
- **Sub-bass (10-42 Hz)**: Impact and rumble for electronic/bass-heavy genres
- **Mid-bass (83-166 Hz)**: Warmth and body, but prone to boom - cut when needed
- **Lower mids (333-577 Hz)**: Muddiness zone - often needs cutting for clarity
- **Midrange (1-2 kHz)**: Vocal presence - boost for forward vocals, cut for atmospheric sound
- **Upper mids (4-8 kHz)**: Clarity and definition - careful with sibilance
- **Treble (8-20 kHz)**: Air and sparkle - boost to compensate for Bluetooth roll-off

### Headphone-Specific Adjustments
- **Bass-heavy headphones** (JBL): Cut mid-bass more aggressively, boost treble more
- **Balanced headphones** (Sennheiser): Moderate adjustments
- **Bright headphones**: Less treble boost, more careful with 4-8 kHz
- **Bluetooth models**: Always compensate for high-frequency roll-off

## Adding New Headphone Profiles

To add support for a new headphone:

1. Research the headphone's frequency response and sound signature
2. Create `headphone_profiles/[Model Name].md` using existing profiles as template
3. Include:
   - Native sound signature (bass/mid/treble characteristics)
   - Connection type (wired/Bluetooth/USB)
   - Known strengths and weaknesses
   - Compensation strategy with frequency-specific guidelines
   - Technical specifications
4. Add to `CONFIG.md` available profiles list
5. Optionally update default target in `CONFIG.md`
