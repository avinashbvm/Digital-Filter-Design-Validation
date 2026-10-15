# Digital Filter Design and Quantitative Validation

## Project Overview

This project demonstrates the design and quantitative evaluation of digital filters using Python. A synthetic signal containing useful low-frequency components and high-frequency interference is generated to study how different filters affect signal quality.

Two filtering approaches are evaluated:

- **Notch filter:** targets interference around 20 Hz.
- **Butterworth low-pass filter:** attenuates frequency components above a 5 Hz cutoff.

The project compares waveform behavior, frequency-domain attenuation, root mean square error (RMSE), and correlation with a clean reference signal.

## Objectives

- Generate a synthetic signal with known frequency components.
- Design a digital notch filter and a Butterworth low-pass filter.
- Evaluate filter performance in the time and frequency domains.
- Measure interference attenuation in decibels.
- Compare filtered outputs using RMSE and correlation.
- Understand the trade-offs between selective interference removal and broader noise suppression.

## Technologies Used

- Python
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook

## Repository Structure

```text
Digital-Filter-Design-Validation/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── filter_validation.ipynb
└── outputs/
    └── plots/
        ├── original_signal.png
        ├── filtered_signals.png
        ├── filter_attenuation.png
        ├── power_spectral_density.png
        └── .gitkeep
```

## Methodology

### 1. Synthetic Signal Generation

A synthetic test signal is constructed from useful components at 1.2 Hz and 3 Hz, with interference components at 20 Hz and 60 Hz.

A corresponding clean reference signal is retained for quantitative evaluation.

### 2. Notch Filter Design

A digital notch filter is designed around 20 Hz with a quality factor of Q = 25.

The objective is to suppress the targeted interference while retaining the other frequency components as much as possible.

### 3. Butterworth Low-Pass Filter

A fourth-order Butterworth low-pass filter with a 5 Hz cutoff is designed to retain the low-frequency components and attenuate higher-frequency interference.

### 4. Quantitative Evaluation

The filter outputs are evaluated using:

- **Attenuation (dB):** measures suppression at selected interference frequencies.
- **RMSE:** measures the difference between a filtered signal and the clean reference.
- **Correlation:** measures the similarity between the filtered output and the clean reference.
- **Time-domain plots:** show changes in waveform shape.
- **Frequency-domain plots:** show how the filters modify the signal spectrum.

## Results

The recorded experiment produced the following results:

| Metric | Notch Filter | Low-Pass Filter |
|---|---:|---:|
| RMSE | 0.1427 | 0.0195 |
| Correlation with clean reference | 0.9818 | 0.9997 |
| Attenuation at 20 Hz | 32.62 dB | 54.62 dB |
| Attenuation at 60 Hz | 0.00 dB | 57.10 dB |

### Interpretation

- The notch filter provides targeted suppression around 20 Hz while largely retaining the 60 Hz component.
- The low-pass filter suppresses both the 20 Hz and 60 Hz components because both lie above its 5 Hz cutoff.
- The low-pass output shows lower RMSE and higher correlation with the clean reference in this particular experiment.
- These results apply to the synthetic test signal and do not establish that the low-pass filter is always superior. Filter selection depends on the desired signal bandwidth and the interference characteristics.

## Visualizations

### Original Signal

![Original signal](outputs/plots/original_signal.png)

### Filtered Signal Comparison

![Filtered signals](outputs/plots/filtered_signals.png)

### Filter Attenuation

![Filter attenuation](outputs/plots/filter_attenuation.png)

### Power Spectral Density

![Power spectral density](outputs/plots/power_spectral_density.png)

## How to Run

1. Clone or download this repository.
2. Install Python and Jupyter Notebook.
3. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Open the notebook:

   ```bash
   jupyter notebook notebooks/filter_validation.ipynb
   ```

5. Run the notebook cells in order.
6. Verify the numerical results and generated plots.

## Limitations

- The experiment uses a synthetic signal rather than a clinical dataset.
- Filter performance depends on the sampling frequency, filter design, signal bandwidth, and interference frequencies.
- A low-pass filter may remove useful signal components if they lie above the selected cutoff.
- Results depend on the reference signal and evaluation methodology.
- This project is for signal-processing education and is not a clinical validation study.

## Future Improvements

- Evaluate additional notch frequencies and quality factors.
- Compare Butterworth, Chebyshev, and other filter designs.
- Test performance under different noise levels.
- Evaluate phase distortion and transient behavior.
- Validate the filters on real sensor data when suitable data are available.

## Author

**Avinash BVM**

B.Tech — Electronics and Communication Engineering

GitHub: https://github.com/avinashbvm
