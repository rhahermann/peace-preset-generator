# Configuration Files

This folder contains the generation workflow configuration and tracking files.

## Files

### Generation Workflow
- **PRESETS_TO_CREATE.md** - Queue of presets to generate. Add music styles here, then run the generator.
- **CLAUDE.md** - Complete documentation of the AI-assisted generation workflow and audio engineering principles.

### Configuration
- **CONFIG.md** - Headphone configuration. Set the default target headphone and view available profiles.

### Tracking
- **CREATED_PRESETS.md** - Catalog of all generated presets with descriptions and engineering notes.

## Usage

1. Add styles to `PRESETS_TO_CREATE.md`
2. Run the generation workflow (requires Claude Code)
3. Generated presets appear in `/output` folder
4. Presets are logged in `CREATED_PRESETS.md`
5. Completed items are cleared from `PRESETS_TO_CREATE.md`

See [`CLAUDE.md`](CLAUDE.md) for detailed workflow documentation.
