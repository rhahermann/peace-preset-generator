# Contributing to Peace Preset Generator

Thank you for your interest in contributing! This project thrives on community input.

## Ways to Contribute

### 1. Add a Device Profile

Help expand support for more devices (headphones, speakers, soundbars, etc):

1. **Research the device**
   - Find frequency response measurements (RTINGS, Crinacle, ASR, manufacturer specs)
   - Note bass/mid/treble characteristics
   - Identify strengths and weaknesses
   - Understand use case (listening distance, room acoustics for speakers)

2. **Create the profile**
   - Copy an existing profile from `device_profiles/[category]/`
   - Fill in technical details
   - Document compensation strategies
   - Include frequency-specific guidance
   - Add device type and channel configuration

3. **Submit**
   - Add profile to `device_profiles/[category]/[Model Name].md`
   - Update `CONFIG.md` with the new model
   - Create a pull request

**Template structure:**
```markdown
# [Model Name]

## Device Type
**[Headphone / Portable Speaker / Desktop Speaker / Soundbar / etc]**

## Channel Configuration
**[2.0 / 2.1 / 5.1 / etc]**

## Native Sound Signature
- Overall character
- Bass response
- Midrange
- Treble
- Connection type

## Use Case Considerations (for speakers)
- Typical listening scenarios
- Room placement impact
- Listening distance

## Compensation Strategy
- What needs correction
- Frequency-specific adjustments
- Genre-specific approaches

## Technical Specifications
- Driver size, impedance, power output, etc.
```

### 2. Share Your Presets

Have a manually-tuned preset that sounds great?

1. **Format it correctly**
   - 13 frequency bands: 10, 21, 42, 83, 166, 333, 577, 1000, 2000, 4000, 8000, 16000, 20000 Hz
   - Quality factor: 0.7 for all bands
   - Follow the `.peace` INI format

2. **Document it**
   - Add to `CREATED_PRESETS.md` with:
     - Date
     - Device model and type
     - Genre/style
     - Your reasoning for the EQ curve

3. **Name it properly**
   - Format: `[Genre] - [Device Model].peace`
   - Example: `Progressive House - Sony WH-1000XM5.peace`
   - Example: `Jazz - JBL Flip 6.peace`

4. **Submit via PR**

### 3. Report Issues

Found something wrong with a preset?

**Open an issue with:**
- Device model and type (headphone/speaker/etc)
- Preset name
- What sounds off (too much bass, harsh highs, etc.)
- Your audio source (streaming quality, file format)
- Your Peace/Equalizer APO version
- For speakers: room size and placement

### 4. Request New Presets

Want a preset for a specific genre/device combo?

**Open an issue with:**
- Device model (must have a profile already, or include research)
- Device type (headphone/speaker/etc)
- Music genre/style
- Reference tracks (optional)
- Any specific preferences

### 5. Improve Documentation

- Fix typos or unclear explanations
- Add examples
- Translate to other languages
- Improve audio engineering explanations

## Code of Conduct

### Be Respectful
- Audio preferences are subjective
- "This sounds bad to me" ≠ "This is objectively wrong"
- Different people have different hearing and preferences

### Be Constructive
- Explain WHY something doesn't work
- Suggest improvements, don't just criticize
- Share your experience and reasoning

### Be Scientific
- Back claims with measurements when possible
- Reference sources (RTINGS, Crinacle, ASR, etc.)
- Understand the difference between technical accuracy and musical preference

## Pull Request Process

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b add-sony-wh1000xm5-profile
   # or
   git checkout -b add-bose-soundlink-profile
   ```
3. **Make your changes**
   - Follow existing file structure
   - Use consistent formatting
   - Test your presets if possible

4. **Commit with clear messages**
   ```bash
   git commit -m "Add Sony WH-1000XM5 headphone profile"
   # or
   git commit -m "Add Bose SoundLink Flex speaker profile"
   ```

5. **Push and create PR**
   ```bash
   git push origin add-sony-wh1000xm5-profile
   # or
   git push origin add-bose-soundlink-profile
   ```

6. **Describe your changes**
   - What you added/changed
   - Why it's needed
   - How you tested it (if applicable)

## Testing Presets

If you're submitting a preset, ideally test it with:

- **Multiple tracks** across the genre
- **Different source qualities** (streaming, lossless)
- **Various volume levels**
- **Extended listening** (not just a quick A/B)

Document your testing in the PR description.

## Audio Engineering Standards

When creating presets, follow these principles:

### Frequency Adjustments
- **Sub-bass (10-42 Hz)**: Impact without boom
- **Bass (42-166 Hz)**: Warmth, avoid muddiness
- **Lower mids (166-577 Hz)**: Clarity, cut when muddy
- **Midrange (1-2 kHz)**: Vocal presence
- **Upper mids (4-8 kHz)**: Definition without sibilance
- **Treble (8-20 kHz)**: Air and sparkle

### General Rules
- Boost conservatively (usually +6 dB max)
- Cut aggressively when needed (can go -6 to -12 dB)
- Always compensate for headphone characteristics first
- Then adjust for genre requirements
- Balance technical accuracy with musicality

### Bluetooth Considerations
- Expect high-frequency roll-off
- Boost treble more than wired equivalents
- Account for codec limitations (SBC, AAC)

## Questions?

Open a [Discussion](https://github.com/rhahermann/peace-preset-generator/discussions) or an [Issue](https://github.com/rhahermann/peace-preset-generator/issues).

## License

By contributing, you agree that your contributions will be licensed under the GNU General Public License v3.0.
