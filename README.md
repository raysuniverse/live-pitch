# Live Pitch

Real-time pitch monitor for speech practice. It shows the musical note you are
speaking on and, optionally, the note of what you are hearing (a coach on a
call, a recording), against your own floor, home and ceiling targets.

**Open:** https://raysuniverse.github.io/live-pitch/
**Demo without a microphone:** https://raysuniverse.github.io/live-pitch/?demo=1

## Features

- Two live readouts: **YOU** (microphone) and **HEAR** (what your computer plays)
- Fixed note-to-colour spectrum, so the same note always has the same colour
- Floor / home / ceiling targets with an instant verdict under your note
- Their levels detected automatically from the heard speech; copy them as your targets
- Scrolling pitch contours in stacked or overlay lanes; 5, 10 or 20 s window
- Minimal view, adjustable size, and a floating always-on-top window (Chrome)
- Session log export as CSV

## Usage

1. Open the page in Chrome, Edge or Safari and press **Start**. Allow the microphone.
2. Drag the handles under *my targets* to set your floor, home and ceiling.
3. To track what you hear, choose a source under *what I hear* (see below), then press **Start** again.

| Key | Action |
|-----|--------|
| ↑ / ↓ | Move all three targets |
| a | Their levels: auto / manual |
| c | Copy their levels to my targets |
| o | Overlay / stacked lanes |
| r | Display range: auto / manual |
| + / − | Size |
| m | Minimal view |
| d | Download the session log |

## Hearing what your computer plays

Browsers can only listen to inputs, so system audio must be routed through a
virtual input device.

- **macOS:** install [BlackHole 2ch](https://existential.audio/blackhole/). In Audio MIDI
  Setup, create a Multi-Output Device containing your headphones and BlackHole, and
  select it as the system output. Choose *BlackHole 2ch* under *what I hear*.
- **Windows:** install [VB-Cable](https://vb-audio.com/Cable/). Set the system output to
  *CABLE Input*, enable *Listen to this device* on your headphones, and choose
  *CABLE Output* under *what I hear*.
- **Audio playing inside Chrome** (a video, a browser-based call): choose *a browser tab*
  and tick *Share tab audio* in the dialog.

## Privacy

All processing happens in the browser. No audio or data is uploaded. Settings are
stored in the browser's local storage, and the session log leaves the device only
when you download it.

## Method

Pitch is estimated with the YIN algorithm on 64 ms frames at 16 kHz (60–500 Hz),
median-smoothed over 250 ms, with an adaptive noise gate and single-frame
octave-error rejection. Notes use A4 = 440 Hz.

## License

MIT. Free to use, copy, modify and redistribute; see [LICENSE](LICENSE).
