# Band-limited oscillator

This notebook implements and visualizes a **band-limited sawtooth oscillator**. The `Oscillator` logic follows the additive approach from Chapter 6, “The Sawtooth Oscillator,” in:

> Hodge, J., & Hollemans, M. (2023). *Creating synthesizer plug-ins with C++ and JUCE*. Independently published.

## What the notebook does

[`band_limited_oscillator.ipynb`](band_limited_oscillator.ipynb) walks through four steps:

1. **Imports** — NumPy for buffers and math, Matplotlib for plotting.

2. **`Oscillator` class** — A sample-by-sample generator with configurable amplitude, frequency, and sample rate. Each call to `next_bandlimited_sample()`:
   - Advances a phase accumulator (`phase_bl`) by `frequency / sample_rate`, wrapping at 1.0.
   - Sums odd harmonics of a sine series (alternating sign, amplitude falling as `1/i`) for every harmonic below Nyquist (`sample_rate / 2`). That Fourier-series construction approximates a band-limited sawtooth instead of a naive discontinuous ramp, which would alias when sampled.
   - Returns the result scaled by `amplitude` via `next_sample()`.

   Default parameters in the notebook: **2 Hz** tone, **1000 Hz** sample rate.

3. **Render a buffer** — Fills a 1000-sample NumPy array by calling `next_sample()` in a loop (one second of audio at the default rate).

4. **Plot** — Draws amplitude vs. time with labeled axes, a title noting frequency and sample rate, and a wide figure so several cycles of the waveform are easy to see.
