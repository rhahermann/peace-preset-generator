# Configuration

## Active Device Profile

**Current Target:** Sennheiser HD 4.40 BT (Headphone)

All new presets will be generated for this device unless otherwise specified.

---

## Available Device Profiles

### Headphones
1. **Sennheiser HD 4.40 BT** - See `device_profiles/headphones/Sennheiser HD 4.40 BT.md`
2. **JBL Tune 520BT** - See `device_profiles/headphones/JBL Tune 520BT.md`

### Speakers - Portable
1. **JBL Flip 6** - See `device_profiles/speakers/portable/JBL Flip 6.md`

### Speakers - Desktop
*(No profiles yet)*

### Speakers - Soundbars
*(No profiles yet)*

### Speakers - Home Theater
*(No profiles yet)*

---

## How to Change Target Device

1. Create a new profile in `device_profiles/[category]/[Model Name].md`
2. Update "Current Target" above
3. New presets will use the active profile

## How to Generate for Specific Device

In `PRESETS_TO_CREATE.md`, use this format:

```
[Genre/Style] @ [Device Model]
```

Examples:
```
Vocal Trance @ Sennheiser HD 4.40 BT
Jazz - Smooth @ JBL Flip 6
Rock @ Default
Electronic - Deep House @ JBL Tune 520BT
```

If no `@ [Model]` is specified, the active target above will be used.
