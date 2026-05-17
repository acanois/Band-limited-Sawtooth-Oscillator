# Band-limited oscillator

These notebooks implement and visualize **band-limited sawtooth** oscillators in Python. The approaches follow *Creating synthesizer plug-ins with C++ and JUCE*:

> Hodge, J., & Hollemans, M. (2023). *Creating synthesizer plug-ins with C++ and JUCE*. Independently published.

## Notebooks

[`band_limited_oscillator.ipynb`](band_limited_oscillator.ipynb) — Chapter 6, “The Sawtooth Oscillator.” Additive synthesis: sums harmonics below Nyquist on each sample. Runs a sample-by-sample loop, then plots the buffer.

Default parameters:
    Frequency: **2 Hz**,
    Sample Rate: **1000**

[`blit.ipynb`](blit.ipynb) — Band-limited impulse train (BLIT). Each sample uses a `sinc` function to generate an impulse train.

Default parameters:
    Frequency: **10 Hz**,
    Sample Rate: **1000**

A real sample rate would never be 1000, but it's a nice, round number for plotting.
