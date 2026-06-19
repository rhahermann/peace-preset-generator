# JBL Flip 6

## Device Type
**Portable Bluetooth Speaker**

## Channel Configuration
**2.0 Stereo** (L/R drivers + dual passive radiators)

---

## Native Sound Signature

### Frequency Response
- **Deep sub-bass (10-42 Hz):** Limited by cabinet size, passive radiators extend down to ~60 Hz
- **Mid-bass (42-166 Hz):** Boosted, punchy - JBL's "signature" bass slam
- **Upper bass (166-333 Hz):** Warm, can become boomy at high volumes
- **Lower midrange (333-577 Hz):** Slightly recessed, makes room for bass
- **Midrange (577-2000 Hz):** Relatively balanced, good vocal clarity
- **Upper midrange (2000-4000 Hz):** Slightly forward for presence
- **Treble (4000-8000 Hz):** Bright, energetic - typical JBL character
- **Upper treble (8000-20000 Hz):** Present but rolls off due to Bluetooth + small tweeters

### Strengths
- Impressive bass for size (passive radiators do heavy lifting)
- Loud, room-filling sound
- Good clarity in midrange despite bass emphasis
- Durable, portable, waterproof (IP67)
- Long battery life

### Weaknesses
- Bass can boom/muddy in small rooms or near walls
- Treble can become harsh at high volumes
- Limited sub-bass extension (physics of small cabinet)
- Bluetooth compression affects upper treble detail
- Volume-dependent response (bass bloats at low volumes due to loudness compensation)

---

## Use Case Considerations

### Typical Listening Scenarios
- **Indoor:** Small to medium rooms, desktop/shelf placement, 1-3m listening distance
- **Outdoor:** Open-air parties, beach/pool, varied distances
- **Volume levels:** Moderate (50-70%) most common, max volume for outdoor use

### Room Placement Impact
- **Near wall/corner:** +3-6 dB bass boost (boundary reinforcement)
- **Center of room:** More balanced, less bass
- **Desktop/shelf:** Proximity effect enhances bass

### Listening Distance
- **Near-field (0.5-1m):** Direct sound, more detail, harsher treble
- **Mid-field (1-3m):** Most balanced, typical use case
- **Far-field (3m+):** Bass dominates, treble rolls off, less detail

---

## EQ Compensation Strategy

### General Principles
1. **Tame mid-bass bloom** - Cut 166-333 Hz to reduce boomy character
2. **Control upper bass** - Moderate cuts at 166 Hz prevent muddiness
3. **Preserve midrange clarity** - Minimal adjustments in 577-2000 Hz (speaker's strength)
4. **Smooth treble peaks** - Gentle cuts at 4-6 kHz to reduce harshness
5. **Recover air and detail** - Boost 8-16 kHz to compensate for Bluetooth roll-off
6. **Respect physical limits** - Don't boost sub-bass below 60 Hz (speaker can't reproduce it, causes distortion)

### Frequency-Specific Guidelines

| Band | Frequency | Typical Adjustment | Reasoning |
|------|-----------|-------------------|-----------|
| 1 | 10 Hz | 0 to +2 dB | Below speaker's capability, minimal boost |
| 2 | 21 Hz | 0 to +2 dB | Below speaker's capability, minimal boost |
| 3 | 42 Hz | +1 to +4 dB | Passive radiator range, moderate boost OK |
| 4 | 83 Hz | 0 to +3 dB | Strong native response, light touch |
| 5 | 166 Hz | -2 to +1 dB | **Boom zone** - often needs cutting |
| 6 | 333 Hz | -2 to +1 dB | Upper bass control, prevents muddiness |
| 7 | 577 Hz | -1 to +2 dB | Lower mid clarity, usually leave neutral |
| 8 | 1000 Hz | -1 to +2 dB | Vocal presence, minimal adjustment |
| 9 | 2000 Hz | 0 to +2 dB | Upper mid clarity, slight boost for detail |
| 10 | 4000 Hz | -2 to +2 dB | Sibilance zone, cut if harsh |
| 11 | 8000 Hz | +2 to +5 dB | Bluetooth roll-off compensation |
| 12 | 16000 Hz | +3 to +6 dB | Air and sparkle recovery |
| 13 | 20000 Hz | +2 to +5 dB | Upper treble extension |

### Genre-Specific Adjustments

**Bass-Heavy Genres (EDM, Hip-Hop, Trap)**
- Keep bass punch but control boom (cut 166 Hz more aggressively)
- Boost sub-bass conservatively (+2-3 dB max at 42 Hz)
- Strong treble boost for hi-hat detail

**Rock/Metal**
- Moderate bass (less boom, more punch)
- V-shaped curve but less extreme than headphones
- Control 4 kHz harshness for cymbal comfort

**Classical/Acoustic**
- Natural, balanced curve
- Minimal bass boost
- Gentle treble extension for air

**Vocal-Focused (Jazz, R&B, Podcast)**
- Flat midrange, light bass reduction
- Cut 166-333 Hz for warmth without boom
- Smooth treble for non-fatiguing listening

---

## Technical Specifications

- **Drivers:** 2x 44mm racetrack-shaped drivers + 2x passive radiators
- **Frequency Response:** 63 Hz - 20 kHz (manufacturer spec)
- **Power Output:** 30W RMS (20W woofer + 10W tweeter)
- **Bluetooth:** 5.1 with SBC codec (no aptX/LDAC)
- **Battery:** 4,800 mAh (up to 12 hours)
- **Waterproof:** IP67 (dust/water resistant)
- **Weight:** 550g

---

## Limitations & Warnings

1. **Sub-bass boost limitation:** Don't exceed +4 dB below 60 Hz - speaker physically cannot reproduce it and will distort
2. **Volume dependency:** These presets assume 50-70% volume; bass will be exaggerated at low volumes, muddy at max volume
3. **Room acoustics matter:** Near-wall placement will add +3-6 dB bass; adjust preset or move speaker
4. **Bluetooth compression:** High-resolution presets won't fully translate through SBC codec
5. **No HPF in Peace format:** Ideally this speaker needs a 50-60 Hz high-pass filter to prevent wasted excursion (requires EqualizerAPO `.txt` format)

---

## Recommended Preset Philosophy

- **Less aggressive than headphones** - Speakers interact with room acoustics
- **Focus on tonal balance** - Don't fight the speaker's character too much
- **Genre matters more** - Same speaker sounds very different with EDM vs Classical
- **Test at target volume** - EQ sounds different at 30% vs 80% volume
