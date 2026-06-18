# Headphone Profile: JBL Tune 520BT

## Target Headphone
**Model:** JBL Tune 520BT (Bluetooth Wireless)  
**Series:** JBL Tune Series (Budget consumer line)

## Native Sound Signature

### Frequency Response Characteristics
- **Overall**: JBL's signature bass-forward "fun" tuning with elevated lows
- **Bass Response**: 
  - Strong emphasis on mid-bass (60-200 Hz) - punchy and prominent
  - Sub-bass (20-60 Hz) present but not as extended as premium models
  - Bass can bleed into lower midrange, creating warmth but potential muddiness
- **Midrange**: 
  - Lower mids (200-500 Hz) slightly elevated due to bass bleed
  - Upper mids (1-3 kHz) relatively balanced but can be slightly recessed
  - Vocals sit slightly behind the mix, not forward
- **Treble**: 
  - Lower treble (4-6 kHz) moderate presence, adequate clarity
  - Upper treble (8-16 kHz) gently rolled off
  - Not harsh or sibilant, but can lack sparkle and air
  - Detail retrieval is adequate but not exceptional
- **Tuning Philosophy**: Consumer-friendly, bass-heavy sound for pop, hip-hop, EDM

### Build & Technical Specs
- **Driver**: 33mm dynamic drivers
- **Frequency Range**: 20 Hz - 20,000 Hz
- **Impedance**: 32 Ω
- **Sensitivity**: ~100 dB SPL/mW
- **Design**: On-ear, closed-back
- **Weight**: ~157g (lightweight)

### Bluetooth Considerations
- **Codecs**: SBC (standard Bluetooth codec, no aptX or AAC optimization)
- **Impact**: 
  - Compressed audio can further reduce treble extension
  - Dynamic range slightly compressed vs wired
  - Latency present (not ideal for gaming/video without delay compensation)
- **Battery Life**: ~57 hours (excellent for budget tier)

## Compensation Strategy

### Known Weaknesses to Address
1. **Excessive mid-bass**: Can create boom and mask details
2. **Rolled-off treble**: Lacks air and sparkle in upper frequencies
3. **Recessed upper mids**: Vocals can sound distant
4. **Bass bleed**: Lower midrange can be muddy

### EQ Approach for JBL Tune 520BT

#### For Balanced/Reference Sound
```
Sub-bass (10-21 Hz):    +2 to +3     → Extend deep bass presence
Mid-bass (42-83 Hz):    -2 to -4     → Reduce boom and bloat
Upper bass (166 Hz):    -3 to -5     → Cut muddiness
Lower mids (333-577 Hz): -2 to -3    → Clean up bass bleed
Midrange (1-2 kHz):     +1 to +3     → Bring vocals forward
Upper mids (4 kHz):     +2 to +4     → Add clarity and presence
Treble (8-16 kHz):      +3 to +6     → Compensate for roll-off, add air
Ultra-high (20 kHz):    +4 to +7     → Extend sparkle
```

#### For Enhanced Bass (EDM/Hip-Hop)
```
Sub-bass (10-21 Hz):    +4 to +6     → Deep rumble
Mid-bass (42-83 Hz):    +1 to +3     → Keep punch but controlled
Upper bass (166 Hz):    -1 to -2     → Prevent excessive mud
Lower mids (333-577 Hz): -3 to -4    → Maintain clarity
Midrange (1-2 kHz):     -1 to +1     → Balanced
Upper mids (4 kHz):     +2 to +3     → Clarity
Treble (8-20 kHz):      +4 to +7     → Brightness to balance bass
```

#### For Vocal-Forward (Pop/Acoustic)
```
Sub-bass (10-21 Hz):    +1 to +2     → Light presence
Mid-bass (42-83 Hz):    -3 to -5     → Reduce significantly
Upper bass (166 Hz):    -4 to -6     → Cut bloat
Lower mids (333-577 Hz): -2 to -3    → Clean foundation
Midrange (1-2 kHz):     +3 to +5     → Emphasize vocals
Upper mids (4 kHz):     +3 to +5     → Vocal clarity
Treble (8-20 kHz):      +3 to +5     → Natural air
```

## Comparison to Sennheiser HD 4.40 BT

| Characteristic | JBL Tune 520BT | Sennheiser HD 4.40 BT |
|----------------|----------------|------------------------|
| Bass quantity | More (mid-bass focused) | Less (sub-bass focused) |
| Bass quality | Punchy but bloated | Tighter, more controlled |
| Midrange | More recessed | Moderately recessed |
| Treble extension | More rolled off | Better extension |
| Detail retrieval | Lower | Higher |
| Sound signature | Bass-heavy warm | V-shaped balanced |
| Price tier | Budget (~$50) | Mid-budget (~$100) |

## User Preference Notes

**To be filled after user testing:**
- User's baseline preset reference: _[Pending]_
- Preferred sound characteristics: _[Pending]_
- Listening preferences: _[Pending]_

## EQ Philosophy Summary

The JBL Tune 520BT requires **more aggressive EQ** than the HD 4.40 BT:
- **Cut mid-bass significantly** to prevent boom
- **Boost treble more** to compensate for greater roll-off
- **Lift upper mids** if vocal presence is desired
- The headphone's natural sound is bass-dominant, so most presets will involve taming lows

## Technical Specifications

- **Type**: On-ear, closed-back
- **Connection**: Bluetooth 5.3
- **Drivers**: 33mm dynamic
- **Frequency Response**: 20 Hz - 20,000 Hz
- **Impedance**: 32 Ω
- **Sensitivity**: ~100 dB SPL/mW
- **Battery**: ~57 hours
- **Charging**: USB-C
- **Weight**: ~157g
- **Foldable**: Yes
- **Controls**: On-ear buttons

## Notes

This profile is based on general JBL Tune 520BT characteristics. For optimal results, user should provide a baseline preset they've tested and liked on this headphone, similar to the "Bluetooth Headset 1.peace" reference for the Sennheiser HD 4.40 BT.

Without user testing data, presets will be generated using the compensation strategies outlined above, but may require user adjustment.
