# 8×8 URA Digital Beamforming Simulation (28 GHz)

MATLAB simulation of digital beamforming for an 8×8 uniform rectangular array (URA) operating at 28 GHz (mmWave), with array factor computation, radiation pattern analysis, and beamforming performance metrics.

## System Parameters

| Parameter | Value |
|---|---|
| Carrier frequency | 28 GHz |
| Wavelength (λ) | 10.71 mm |
| Element spacing | λ/2 |
| Array size | 8 × 8 (64 elements) |
| Element pattern | Isotropic |
| Steering angle (Azimuth) | 30° |
| Steering angle (Elevation) | 20° |
| Sampling frequency | 100 MHz |
| Test signal frequency | 5 MHz |

## Requirements

- MATLAB (tested on R2017 and later)
- Signal Processing Toolbox (`findpeaks`)
- Phased Array System Toolbox or Communications Toolbox (`physconst`)

## How to Run

1. Open `beamforming_sim.m` in MATLAB
2. Run the script — no external inputs required
3. Six figure windows will generate automatically:
   - Array geometry
   - Beamforming weights (magnitude & phase)
   - Radiation patterns (azimuth cut, elevation cut, 2D heatmap, polar plot)
   - Time-domain signal comparison
   - Beamforming gain vs. angle
4. Performance metrics print to the Command Window

## Repository Structure

```
├── beamforming_sim.m          # Main simulation script
├── figures/                   # Exported result plots
│   ├── array_geometry.png
│   ├── beamforming_weights.png
│   ├── radiation_patterns.png
│   ├── signal_comparison.png
│   └── beamforming_gain.png
└── results/
    └── performance_summary.md # Numeric results (directivity, beamwidth, SLL, etc.)
```

## Results

### Array Geometry
8×8 planar array with λ/2 element spacing, centered at the origin.

![Array Geometry](figures/array_geometry.png)

### Beamforming Weights
Magnitude and phase of the normalized steering weights applied to each element.

![Beamforming Weights](figures/beamforming_weights.png)

### Radiation Patterns
Azimuth cut, elevation cut, 2D array factor heatmap, and polar plot — beam steered to (Az = 30°, El = 20°).

![Radiation Patterns](figures/radiation_patterns.png)

### Signal Comparison
Received signal at a single element vs. the combined beamformed output, showing SNR improvement.

![Signal Comparison](figures/signal_comparison.png)

### Beamforming Gain vs. Angle
Directivity as a function of azimuth and elevation angle.

![Beamforming Gain](figures/beamforming_gain.png)

See [`results/performance_summary.md`](results/performance_summary.md) for the full numeric summary (maximum directivity, 3-dB beamwidth, side lobe level, and steering error).

## Notes

- Steering vector and beamforming weights are implemented as anonymous functions for compatibility with older MATLAB versions.
- Additive complex Gaussian noise is included to demonstrate beamforming SNR gain.
