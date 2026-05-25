# MIDI Matrix Monitor 1.0.4 build 1

Released: 26 May 2026

This update improves pitch bend display behaviour for MIDI guitar, wide-range pitch bend, and MPE-style setups.

## Highlights

- Added a new **BEND BEHAVIOUR** section in Settings.
- Added **Source Bend Range** to match the pitch bend range used by your controller, pitch-to-MIDI software, or synth.
- Added **Advanced Meter Scaling**, OFF by default.
- Added optional **Meter Display Range** when Advanced Meter Scaling is enabled.
- Added **No Bends / 0** as a safe neutral source range.
- Improved pitch bend meter scaling so normal MIDI guitar workflows remain simple, while MPE/wide-range users can zoom in on subtle bends.
- Pitch bend text, logs, and exports now report the true musical bend amount based on Source Bend Range.
- Bend Behaviour settings are now saved and restored with user presets / monitor setups.
- Older saved setups remain backward compatible.

## Notes

For standard MIDI guitar or older synth workflows, leave **Advanced Meter Scaling** OFF and set **Source Bend Range** to match your pitch-to-MIDI or synth setup.

For MPE or wide-range setups such as `+/-48`, enable **Advanced Meter Scaling** and choose a smaller **Meter Display Range** if subtle bends are hard to see.

Full notes in release .zip file.

-----------------------------------------------------------------------------------------------------------------

# MIDI Matrix Monitor 1.0.3

Released: 23 May 2026

MIDI Matrix Monitor 1.0.3 focuses on workflow polish, toolbar behaviour, hotkeys, startup/reset terminology, licensing presentation, and continued refinement of compact single-channel monitoring.

## Highlights

- Added hotkey support for key monitoring controls.
- Improved toolbar layout and control behaviour.
- Refined Settings terminology for startup and reset actions.
- Improved separation between startup state and user setup presets.
- Added clearer support and website entries in Settings.
- Continued work on single-channel compact view.

## New and Improved

### Hotkeys

- Added keyboard shortcuts for common monitoring actions.
- Improved shortcut handling so arrow keys no longer accidentally trigger channel-direction changes while editing custom channel names.

### Startup and Reset

- Renamed the former default-state controls to clearer startup/reset terminology.
- Updated Settings wording:
  - `DEFAULTS` is now `STARTUP & RESET`
  - `Save Default` is now `Save Startup State`
  - `Load Default` is now `Load Startup State`
- Improved status messages for saving, loading, and resetting startup state.
- Clarified that startup state is separate from user setup presets.

### Toolbar and Layout

- Improved monitoring input pill sizing so long MIDI input names no longer distort the toolbar.
- Improved toolbar balance after recent app title/header changes.
- Refined panic, monitoring, and toolbar control placement.
- Improved Settings menu usability on smaller laptop displays.

### Single-Channel Compact View

- Added a maximum-width cap for single-channel compact mode.
- Improved window resizing behaviour when switching between single-channel and multi-channel layouts.
- Improved layout behaviour when Global Stream is shown or hidden.

> **Note:** Single-channel compact view is still a work in progress and may receive further layout and selection refinements in future versions.

### Licensing and Trial

- Continued refinement of trial and license-related presentation.
- Confirmed that the release configuration uses the live Lemon Squeezy checkout link.
- Retained the 14-day trial period and 14-day offline grace period.

## Fixes

- Fixed an issue where the monitoring input pill could become too responsive to long device names.
- Fixed keyboard shortcut interference while editing custom channel names.
- Improved consistency of Settings labels and wording.
- Improved toolbar accessibility wording and button presentation.
- Improved layout behaviour on smaller displays.
- Improved startup/reset wording so it is clearer that startup state is separate from user setup presets.

## Known Issues

- Single-channel compact view remains a work in progress.

## Support

For support, contact:

vaultnaemsae@icloud.com

Website:

https://vaultnaemsae.com
