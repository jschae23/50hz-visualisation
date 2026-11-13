# 50 Hz

An interactive visualization of a 50 Hz sine wave: fifty complete cycles per second, so one cycle lasts exactly 20 milliseconds. 50 Hz is the mains frequency used across Europe, Asia, Africa and much of South America.

<img width="1036" height="782" alt="image" src="https://github.com/user-attachments/assets/c148bba8-0773-43f0-b2bf-ae395a71ecf2" />

**Live demo:** `[https://<username>.github.io/<repo>/](https://jschae23.github.io/50hz-visualisation/)`

## What it shows

- **Oscilloscope view.** Three cycles (60 ms) of the wave, with a playhead that traces it out.
- **Rotating arrow.** One turn per cycle. Its height is the wave's value at that moment.
- **Slow motion.** A slider from real time up to 1000× slower. The default of 50× slower makes one cycle take one second.
- **Readouts.** Current time, phase in degrees, and value.
- **Sound.** A "Hear it" button plays a 50 Hz tone with the Web Audio API. Use headphones or a subwoofer, since most laptop and phone speakers can't reproduce 50 Hz.

## Run it locally

No build step and no dependencies. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Publish on GitHub Pages

1. Put `index.html` (and this README) in the root of a GitHub repository.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute or so the site is live at `https://<username>.github.io/<repo>/`.

## Customize

Everything is in `index.html`.

| What | Where |
| --- | --- |
| Frequency | `F = 50` at the top of the script |
| Visible time window | `WIN = 0.060` (seconds) |
| Colors | CSS variables in `:root`, with dark-mode values in the `prefers-color-scheme` block |
| Slow-motion range | `min` and `max` on the `#slow` slider (a power of ten, so `3` means 1000×) |

Changing `F` also changes the labels that say 50 Hz and 20 ms, so update the text in the heading and readouts to match.

## Accessibility

The page follows the system light or dark setting. If reduced motion is requested, it starts paused. Controls have visible keyboard focus.

## License

MIT. Use it however you like.
