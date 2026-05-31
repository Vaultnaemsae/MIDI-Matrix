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

