# MIDI Matrix Monitor 1.0.9

Version 1.0.9 delivers a major refinement of window resizing and screen-size compatibility, particularly for users working on 1080p displays.

## Highlights

- Restored the ability to display all 16 MIDI channels on a 1920 × 1080 display in Horizontal mode when the Global MIDI Stream is collapsed.
- Improved Vertical mode so all 16 channel rows can fit more effectively on smaller displays, including when the macOS Dock is visible.
- Added more intelligent adaptive sizing for channel columns and rows.
- Improved use of available space when manually resizing the application window.

## Window and layout improvements

- Horizontal channel columns now resize dynamically according to the available window width.
- Wider windows distribute additional space evenly across the channel display instead of leaving unused black space.
- When the Global MIDI Stream is visible, it retains a practical fixed width while the channel monitor uses the remaining space.
- When the Global MIDI Stream is collapsed, the channel monitor expands to use the full window width.
- Improved Fit Window behaviour while preserving manual resizing.
- Retained horizontal and vertical scrolling as fallbacks for genuinely constrained window sizes.
- Improved layout consistency when switching between Horizontal, Vertical and Single Channel views.

## Vertical view improvements

- Reduced unnecessary vertical spacing on constrained displays.
- Improved adaptive row sizing while maintaining readable channel information.
- Prevented the final channel row from being clipped at the bottom of the screen in common 1080p configurations.

## MIDI input selector improvements

- Long MIDI input-device names now truncate cleanly instead of colliding with the input connector icon.
- The connector icon now retains its proper size and spacing.
- Full input names remain available through the input-selection menu and tooltip.

## Bug fixes

- Fixed a regression that reduced the number of visible Horizontal channels from 16 to approximately 14 on 1080p displays.
- Fixed unused black space appearing when the application window was expanded on higher-resolution monitors.
- Fixed incorrect width allocation that caused the Global MIDI Stream area to consume excessive space.
- Fixed mismatches between calculated layout dimensions and the actual rendered channel display.
- Improved window sizing calculations across different monitor resolutions and Dock configurations.

--------------------------------------------------

# MIDI Matrix Monitor 1.0.8 

— What’s New

## New BPM Display

MIDI Matrix Monitor can now show the tempo of incoming MIDI Clock directly in the main header.

When a MIDI Clock signal is detected, the app displays a clear BPM value such as `120 BPM`. A small white pulse light flashes with the beat, giving quick visual feedback that clock is being received.

The BPM display is designed to stay stable and readable, rather than constantly flickering from tiny timing variations.

## Choose a Separate Clock Source

You can now choose where MIDI Matrix Monitor gets its MIDI Clock from.

This is useful if you want to monitor MIDI notes from one app or device, while reading tempo from another. For example, you can monitor MIDI Guitar 3 while taking clock from your DAW.

Clock Source options include:

- Auto
- Any available MIDI input port

Clock Source choices can also be saved with user presets.

## Improved Selector Controls

The main selector menus are now easier to use from the keyboard.

- Press `I` for MIDI Input.
- Press `B` for BPM / Clock Source.
- Press `K` for Panic Destination.

When a selector is open, you can use the arrow keys to move through the list, press Return to select, or press Escape to close it.

## Safer Panic Button

The Panic button is now harder to trigger accidentally.

- Single-click opens the Panic Destination selector.
- Double-click sends Panic.
- `⌘.` still sends Panic immediately.

This makes it easier to choose where Panic messages are sent while keeping emergency access available.

## Better All Inputs Monitoring

When monitoring all MIDI inputs, the Global Stream can now show which device or app each event came from.

This makes it easier to understand complex MIDI routing and spot where messages are coming from.

The old label `All Inputs (Diagnostic)` has been simplified to `All Inputs`.

## Cleaner Interface

This update also includes several small interface improvements:

- The BPM display now uses a neutral white/light grey style.
- The Channel Selector now starts hidden by default.
- `PCs` has been renamed to `Program Changes`.
- Pin controls now use simpler labels: `Pin (P)` and `Unpin (P)`.
- Selector menus have been cleaned up and made more consistent.
- Several old helper messages and unused interaction paths were removed.
________________________________________________________________________________________________________________________

# MIDI Matrix Monitor 1.0.7

This update fixes MIDI Clock visibility in the Global MIDI Stream.

## Bug fixes

* Fixed an issue where MIDI Clock messages could be received and parsed but not displayed in the Global MIDI Stream.
* MIDI Clock now appears correctly as a channel-less realtime MIDI event.
* MIDI Clock events are shown with channel --, rather than being incorrectly routed through channel-specific handling.
* MIDI Clock no longer depends on per-channel note, CC, meter, or activity display paths.

Realtime MIDI message handling

MIDI Matrix Monitor now correctly logs channel-less MIDI realtime messages globally, including:

* Clock
* Start
* Continue
* Stop

These messages are displayed in the Global MIDI Stream and do not affect per-channel monitor activity.

Note for saved setups

Fresh/default monitor setups now have realtime/Clock display enabled by default.

Older saved monitor setups may still have realtime messages hidden if they were saved with that filter disabled. If MIDI Clock does not appear after updating, enable the Clock/realtime filter in the Global MIDI Stream settings and save the setup again.

__________________________________________________________________________________________________________________________________________________________

# MIDI Matrix Monitor 1.0.6

Build 3

This update focuses on major usability improvements to channel visibility, single-channel inspection, horizontal/vertical layouts, and watched CC display.

## Highlights

### New Multi Channel / Single Channel workflow
- Replaced the old channel-count style control with a clearer **Multi Channel / Single Channel** toggle.
- Multi Channel mode now uses a dedicated **Visible Channels** selector.
- Single Channel mode now includes a compact 2×8 channel selector above the inspected channel card.
- The app remembers the last inspected channel during the current session when switching between Multi Channel and Single Channel views.

### Visible Channels selector
- Added a top-level 1–16 channel selector for multi-channel visibility.
- Active channels are highlighted.
- Clicking a channel number toggles that channel’s visibility.
- Added a collapsible **Visible Channels** header with chevron show/hide control.
- Added keyboard shortcut **C** for showing/hiding the Visible Channels selector.

### Improved horizontal channel layout
- Replaced repeated per-card watched CC labels with a shared far-left label column.
- Added labels for Program Changes, Notes, watched meters, and Events.
- Removed redundant per-card eye icons from horizontal channel cards.
- Improved horizontal card sizing so low channel counts no longer stretch into oversized cards.
- Added maximum card-width rules and centered low-count channel rows.
- Made normal multi-channel minimum window width more content-aware, allowing smaller layouts to shrink further.

### Watched CC label improvements
- Added a **Watched CC Label Style** setting.
- New options:
  - **Names + CC numbers**
  - **CC numbers only**
- Improved watched CC label formatting so CC numbers remain visible when names are long.
- Restored and standardised many MIDI CC names that were previously shown as undefined or overly compact.

### Vertical mode improvements
- Reworked the vertical meter block order.
- Pitch Bend now anchors the first row.
- Pressure now anchors the second row.
- Watched CCs fill the remaining meter cells in selected order.

### Program Change and Notes display cleanup
- Improved Program Change visibility in compact horizontal cards.
- Removed redundant  prefixes inside Program Change boxes where the shared label column already identifies the row.
- Changed the shared label from **Note** to **Notes**.
- Hid redundant in-card labels where the shared label column already provides the context.

### Toolbar and icon refinements
- Improved Multi Channel / Single Channel toolbar iconography.
- Updated Multi Channel icon to better represent a multi-channel matrix/grid rather than horizontal/vertical layout.
- Reordered toolbar controls so the channel mode control appears before the Horizontal/Vertical layout control.
- Settings button now indicates its active state more clearly.

### Cleanup
- Removed dead visibility popover code left behind by the channel-view redesign.
- Removed obsolete pending single-channel selection code.
- Cleaned up old channel-count UI paths that were no longer used.

### Bug fixes
Fixed an issue where very large MIDI input device lists could be clipped on smaller displays, preventing some ports from being reached or selected.

The MIDI input picker is now scrollable when the number of available inputs exceeds the available screen space, making long device lists usable on laptop displays and smaller windows.

The MIDI Panic destination picker now uses the same scrollable long-list behavior, so large output destination lists remain reachable and selectable on smaller displays.

### Notes

This release significantly changes the way channel visibility and single-channel inspection are controlled. The core MIDI monitoring behaviour is unchanged, but the interface is now more direct:

- Use **Multi Channel** to monitor multiple channels.
- Use the **Visible Channels** selector to choose which channels are shown.
- Use **Single Channel** to inspect one channel in detail.
- Use the 2×8 selector in Single Channel mode to switch inspected channels.

