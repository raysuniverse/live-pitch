# Live Pitch

Live pitch monitor for speech practice. **YOU** is the note you are speaking on;
**HEAR** is the note of what your computer plays (a coach on a call, a clip).
Both are drawn against your own floor / home / ceiling targets.

**Open:** https://raysuniverse.github.io/live-pitch/ · **Demo (no mic):** https://raysuniverse.github.io/live-pitch/?demo=1

## Use

1. Press **▶ Start** and allow the microphone.
2. Drag the handles under **◎ my targets** to set floor, home and ceiling.
3. To track what you hear, pick a source under **what I hear** (see routing below).

Every view has the same two control rows:

- **Under the title:** Start / restart · minimal or full view · float — and on the right **▾ contour** (show / hide the plot) · **stack/overlay** (two lanes or one shared lane). The active choice is blue and bold.
- **Above the contour:** **size** (zoom) · **note** (height of the note + Hz block) · **contour** (plot height). These heights are fixed once set, so nothing jumps while you speak.

Views: full page, **▭ minimal** (notes + contour only), and **⧉ float** (a small always-on-top window, Chrome). Settings remember themselves per view.

| Key | Action |
|-----|--------|
| ↑ / ↓ | move all three targets |
| a | their levels: auto / manual |
| c | copy their levels to my targets |
| o | stack / overlay |
| r | display range: auto / manual |
| + / − | size · [ / ] contour height |
| m | minimal view · d download the log (CSV) |

The same keys work inside the float (there, o / + − / [ ] change the float's own view, and **s** starts).

## Hearing what your computer plays

Browsers can only listen to inputs, so system audio must come back through a virtual input.

- **macOS:** install [BlackHole 2ch](https://existential.audio/blackhole/). In Audio MIDI Setup make a Multi-Output Device with your headphones **and** BlackHole, set it as the system output, and choose *BlackHole 2ch* under *what I hear*. Check BlackHole's own volume is at maximum, and prefer the built-in mic over AirPods so the device stays at 48 kHz.
- **Windows:** install [VB-Cable](https://vb-audio.com/Cable/); output to *CABLE Input*, listen through your headphones, choose *CABLE Output* under *what I hear*.
- **Audio inside Chrome:** choose *a browser tab* and tick *Share tab audio*.

If HEAR reads "silent" or "very quiet", the routing or the loopback volume is the problem, not the page.

## Privacy

Everything runs in the browser. No audio or data leaves the device; settings live in local storage and the log only when you download it.

## Method

YIN pitch estimation on 64 ms frames at 16 kHz (60–500 Hz), 250 ms median smoothing, noise gate, single-frame octave-error rejection. A4 = 440 Hz.

## License

MIT — see [LICENSE](LICENSE).
