# SyntheticECG

### Project Overview:
This project is focused on processing and synthesizing electrocardiogram (ECG) signals using Python and several libraries, including `numpy`, `matplotlib`, `wfdb`, and `scipy`. The primary goal is to create synthetic ECG signals based on real-world ECG data, with capabilities to resample, filter, and manipulate these signals. The synthesized signals can be used for further analysis or as a basis for testing algorithms in medical data analysis.

### Key Components:

1. **Data Loading and Preprocessing**:
   - The project starts by loading ECG data from multiple files using the `wfdb` library. Each ECG file is read into a format that allows easy access to individual leads (channels) and annotations.
   - Baseline drift, a common issue in ECG signals, is removed using a Fast Fourier Transform (FFT)-based high-pass filter.
   - The QRS complexes, T waves, and P waves are identified, and their start and end points are recorded for further processing.

2. **Signal Resampling**:
   - The function `convert_freq` is provided to resample the ECG signals from their original frequency to a target frequency. This is useful for standardizing the sampling rate across different datasets or simulating different acquisition conditions.

3. **Interval Extraction**:
   - The `extract_block_intervals` function extracts specific intervals between the QRS complex, T waves, and P waves. These intervals are crucial for understanding the temporal relationships between different components of the ECG signal and are used later in the synthesis process.

4. **ECG Signal Synthesis**:
   - A key part of the project is the `concatenate_pieces` function, which generates synthetic ECG signals by concatenating real segments of ECG signals with random modifications. This approach allows for the creation of realistic synthetic data that can mimic the variability found in actual ECG signals.
   - The synthetic signals maintain the overall structure of real ECG signals while introducing variability in the timing and morphology of the waves, making them useful for testing and development purposes.

5. **Visualization**:
   - The project includes extensive visualization using `matplotlib`. Both synthetic and actual ECG signals are plotted, with annotations marking the positions of QRS complexes, T waves, and P waves. This visual comparison helps in validating the synthetic signals against real ECG data.

6. **Interval Analysis**:
   - RR intervals (time between successive QRS complexes) and QT intervals (time from the start of the QRS complex to the start of the T wave) are calculated, providing insights into the heart's rhythm and electrical activity.

### Project Structure:
- **`convert_freq` Function**: Resamples ECG data to a different frequency.
- **`prominent_peak` Function**: Identifies the most prominent peaks in the ECG signal.
- **`extract_block_intervals` Function**: Extracts intervals between ECG components (QRS, T, P waves).
- **`concatenate_pieces` Function**: Generates synthetic ECG signals by combining real segments with random modifications.
- **Main Script**:
  - Loads and preprocesses ECG data.
  - Applies filtering and identifies key ECG components.
  - Synthesizes new ECG signals and visualizes the results.

### Applications:
This project is particularly useful in the following scenarios:
- **Medical Data Analysis**: Provides a basis for developing and testing algorithms for ECG signal analysis, such as anomaly detection or heart rate variability analysis.
- **Educational Purposes**: Offers a hands-on example of ECG signal processing, which can be used in teaching signal processing techniques or medical data analysis.
- **Synthetic Data Generation**: Generates realistic synthetic ECG signals that can be used in scenarios where real data is scarce or for augmenting existing datasets.

### Getting Started:
- **Dependencies**: Ensure that Python and the required libraries (`numpy`, `matplotlib`, `wfdb`, `scipy`) are installed.
- **Running the Code**: The main script can be executed to load ECG data, process it, and generate synthetic signals. Visualization is included to compare the real and synthetic signals.

This project is a comprehensive framework for ECG signal processing and synthesis, offering tools for both analysis and data augmentation. It can serve as a foundational tool for anyone working in the field of medical signal processing.
