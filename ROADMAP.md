# Peace Equalizer Preset Generator - Roadmap

## Vision
Expand from headphone-only presets to a universal audio device EQ generator supporting any playback device with genre-specific optimization.

---

## Phase 1: Device Architecture Refactor ✅ COMPLETE
**Goal:** Make architecture device-type agnostic

### Tasks
- [x] Restructure `device_profiles/` with subdirectories:
  - `headphones/`
  - `speakers/portable/`
  - `speakers/desktop/`
  - `speakers/soundbars/`
  - `speakers/home-theater/`
- [x] Add device type metadata to profiles (headphone/speaker/soundbar/etc)
- [x] Add channel configuration field (2.0, 2.1, 5.1, 7.1)
- [x] Create JBL Flip 6 speaker profile (stereo, portable)
- [x] Update CONFIG.md to support device type selection
- [x] Update CLAUDE.md with new architecture
- [x] Preset filename format already correct: `[Genre] - [Device].peace`
- [ ] Test generation workflow with both headphones and speakers (NEXT STEP)

### Output Format
Still using `.peace` files (parametric EQ only)

---

## Phase 2: Filter Support 🔮 PLANNED
**Goal:** Add proper filtering for speakers (HPF, LPF, shelving, notch)

### Why
- Small speakers need HPF to prevent distortion from inaudible sub-bass
- Subwoofer systems need LPF crossovers
- Cabinet resonances need notch filters
- Shelving filters are more natural for broad tonal adjustments

### Tasks
- [ ] Research EqualizerAPO `.txt` config file format
- [ ] Add filter specifications to device profiles:
  - HPF cutoff frequency (e.g., 50 Hz for small speakers)
  - LPF for subwoofer crossovers (80-120 Hz)
  - Known resonance frequencies for notch filters
- [ ] Implement `.txt` config generator (alongside `.peace` format)
- [ ] Add filter type selection to preset generation
- [ ] Document filter usage in CLAUDE.md

### Output Format Options
- **Option A:** Generate both `.peace` (simple) + `.txt` (advanced with filters)
- **Option B:** Switch entirely to `.txt` format
- **Option C:** User selectable per preset

---

## Phase 3: Multi-Channel Support 🔮 FUTURE
**Goal:** Support surround sound systems (5.1, 7.1)

### Challenges
- Each channel needs independent EQ:
  - Center channel (dialogue-focused)
  - Front L/R (full-range)
  - Rear/Surround (ambient)
  - Subwoofer (LFE)
- Genre requirements differ per channel
- Complexity increases significantly

### Tasks
- [ ] Research multi-channel EqualizerAPO configuration
- [ ] Define channel-specific EQ strategies:
  - Center: clarity, vocal presence
  - Front L/R: genre-appropriate full curve
  - Surround: atmospheric, reduced aggression
  - Sub: crossover + genre bass curve
- [ ] Add channel mapping to device profiles
- [ ] Implement multi-file output (one config per channel)
- [ ] Test with real 5.1/7.1 systems

### Output Format
EqualizerAPO `.txt` with channel routing (requires Phase 2 completion)

---

## Future Considerations

### Device Categories to Add
- [ ] IEMs (In-Ear Monitors)
- [ ] Studio monitors
- [ ] Car audio systems
- [ ] Gaming headsets
- [ ] TV audio (built-in speakers)
- [ ] Bluetooth receivers/DACs

### Feature Ideas
- [ ] Room correction integration (measure + compensate)
- [ ] Volume-dependent EQ curves
- [ ] A/B testing mode (compare presets)
- [ ] Preset interpolation (blend two genres)
- [ ] Community preset sharing
- [ ] Visualization of EQ curves (frequency response graphs)

---

## Notes
- **Backward compatibility:** Existing `.peace` presets remain valid
- **Device profiles:** Each new device type needs research on frequency response, driver specs, and use cases
- **Testing:** Always verify on real hardware when possible
