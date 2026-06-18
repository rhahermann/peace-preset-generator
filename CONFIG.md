# Configuration

## Active Headphone Profile

**Current Target:** Sennheiser HD 4.40 BT

All new presets will be generated for this headphone unless otherwise specified.

---

## Available Headphone Profiles

1. **Sennheiser HD 4.40 BT** - See `headphone_profiles/Sennheiser HD 4.40 BT.md`
2. **JBL Tune 520BT** - See `headphone_profiles/JBL Tune 520BT.md` 

---

## How to Change Target Headphone

1. Create a new profile in `headphone_profiles/[Model Name].md`
2. Update "Current Target" above
3. New presets will use the active profile

## How to Generate for Specific Headphone

In `PRESETS_TO_CREATE.md`, use this format:

```
[Genre/Style] @ [Headphone Model]
```

Examples:
```
Vocal Trance @ Sennheiser HD 4.40 BT
Jazz - Smooth @ Sony WH-1000XM5
Rock @ Default
```

If no `@ [Model]` is specified, the active target above will be used.
