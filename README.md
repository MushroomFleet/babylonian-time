# 𒀭 Babylonian Time

**A working clock written in Mesopotamian cuneiform numerals: base-60 timekeeping, the way the scribes of Babylon counted.**

Babylonian Time is a single-page HTML clock that reads your system time and shows it with the cuneiform number signs used in ancient Mesopotamia. Each digit is impressed into a clay tablet, wedge by wedge, and animates as the time changes.

It's a small project that sits between history, mathematics and design. It shows how the base-60 system works, and it makes a nice ambient display for a second monitor.

---

## Why base 60?

We still count time in 60s (60 seconds, 60 minutes) because of the Babylonians. Their number system was **sexagesimal** (base 60), and it was built from just two signs:

| Sign | Name | Value |
|------|------|-------|
| 𒁹 upright wedge | *diš* | 1 |
| 𒌋 corner wedge | *u* (Winkelhaken) | 10 |

Any number from 1 to 59 is written by grouping corner wedges (tens) followed by upright wedges (units). So **37** is three corner wedges and seven upright wedges. That makes one sign a single base-60 "digit", which is exactly what hours, minutes and seconds need.

The Babylonians had **no zero digit**. An empty place was simply left as a gap, and later scribes used a pair of slanted wedges as a placeholder. The clock lets you choose either.

---

## Features

- **Live system clock** in 24-hour `HH:MM:SS`, one cuneiform numeral per unit
- **Animated impressions:** each new numeral is pressed into the clay, with tens wedges landing before units, and the old sign is smoothed away
- **Two time modes**
  - **Western:** hours, minutes and seconds
  - **Day fraction:** the time of day as a single sexagesimal fraction, in the style of Babylonian astronomical texts. The first place counts 60ths of a day (24 min), the second 60ths of that (24 s), the third 60ths again (0.4 s). It's shown in modern scholarly notation as well, e.g. `0;19,05,22 of a day`.
- **Two layouts**
  - **Three tablets:** one clay tablet per unit, with separators
  - **One tablet:** all three numerals on a single long tablet separated by gaps, as they'd be written in a real text
- **Zero options:** an empty space (historically accurate) or the Late Babylonian placeholder sign
- **Arabic numeral guide** that you can turn on while learning and turn off once you can read the wedges
- **Full-screen mode** and a responsive layout that works on desktop and mobile
- **Remembers your settings** in the browser
- **Respects `prefers-reduced-motion`**
- **No dependencies, no build step:** one self-contained HTML file with all glyphs embedded as vector paths

---

## Getting started

Download the HTML file and open it in any modern browser. There's nothing to install and nothing to build.

```bash
git clone https://github.com/MushroomFleet/babylonian-time.git
cd babylonian-time
# then open sexagesimal-clock.html in your browser
```

To host it, drop the file on any static host (GitHub Pages, Netlify, etc.).

---

## How the glyphs were made

The 59 numerals were cropped from a reference chart of cuneiform numbers 1–59. Each one was:

1. Located on the chart and trimmed to its ink bounds, leaving out the printed labels
2. Upscaled and traced into a vector outline, so it stays sharp at any display size
3. Split into wedge groups (tens and units), so the clock can animate them in sequence

The resulting assets are included for reuse:

| Asset | Description |
|-------|-------------|
| `png/01.png` … `png/59.png` | Transparent PNG crops of each numeral |
| `svg/01.svg` … `svg/59.svg` | Scalable vector versions |
| `glyphs.json` | The vector path data used by the clock, keyed by value |
| `crop.py` | The script that crops and vectorises the chart |

The zero placeholder isn't in the source chart. It's drawn separately as a pair of slanted wedges.

---

## A note on accuracy

This is a creative, educational take on the system, not a reconstruction of a historical instrument. The Babylonians didn't have mechanical clocks or a 24-hour day. They divided the day and night into watches, and astronomers measured time in *UŠ* (four of our minutes) and *bēru* ("double hours"). Their day also began at sunset, while this clock counts from midnight. The **Day fraction** mode is the closer of the two to how Babylonian astronomers wrote time; the **Western** mode uses the cuneiform signs to show the clock you already know.

---

## 📚 Citation

### Academic Citation

If you use this codebase in your research or project, please cite:

```bibtex
@software{babylonian_time,
  title = {Babylonian Time: An animated cuneiform clock using Mesopotamian base-60 numerals},
  author = {Drift Johnson},
  year = {2026},
  url = {https://github.com/MushroomFleet/babylonian-time},
  version = {1.0.0}
}
```

### Donate:

[![Ko-Fi](https://cdn.ko-fi.com/cdn/kofi3.png?v=3)](https://ko-fi.com/driftjohnson)
