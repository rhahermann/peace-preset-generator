# Examples

This folder contains sample Peace Equalizer preset files for reference.

## Files

- **Bluetooth Headset 1.peace** - Example preset showing the `.peace` file format structure

## Format Reference

Each `.peace` file contains:
```ini
[Frequencies]
Frequency1=10
Frequency2=21
...
Frequency13=20000

[Gains]
Gain1=<dB value>
Gain2=<dB value>
...
Gain13=<dB value>

[Qualities]
Quality1=0.7
Quality2=0.7
...
Quality13=0.7
```

All generated presets follow this format and are saved to the `output/` folder.
