# Band-limited oscillator

This notebook implements and visualizes a **band-limited sawtooth oscillator**. The `Oscillator` logic follows the additive approach from Chapter 6, “The Sawtooth Oscillator,” in:

> Hodge, J., & Hollemans, M. (2023). *Creating synthesizer plug-ins with C++ and JUCE*. Independently published.

## What the notebook does

[`band_limited_oscillator.ipynb`](band_limited_oscillator.ipynb) runs a sample-by-sample loop that fills a buffer, and then plots the contents of that buffer.

Default parameters: 
    Frequency: **2 Hz**, 
    Sample Rate: **1000** 
    
A real sample rate would never be 1000, but it's a nice, round number for plotting.
