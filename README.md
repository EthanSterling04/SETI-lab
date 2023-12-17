# SETI Lab

## Overview

Welcome to the Search for Extraterrestrial Intelligence (SETI) Lab! This project involves optimizing a signal processing code base by parallelizing using POSIX thread libraries, AVX-512 SIMD vector instructions, the OpenMP API, and compiler optimizations for a total speed-up of 60x.

## Lab Description

SETI aims to find alien civilizations through radio wave emissions. The lab focuses on analyzing signal data from radio telescopes using parallel processing techniques. Your task is to develop a program that searches for signs of intelligence in raw signals from broadband receivers.

## Optimizations

Two key optimizations to implement are `p_band_scan` and `p_convolve_and_compute_power`. These optimizations should enhance the program's performance and enable parallel computation.

* [p_band_scan](https://github.com/EthanSterling04/SETI-lab/blob/main/p_band_scan.c)
* [p_convolve_and_compute_power](https://github.com/EthanSterling04/SETI-lab/blob/main/filter.c)

## Project Structure

The project includes the following elements:

- **README.md**: Describes project details and instructions.
- **Makefile**: Compiles the code and includes necessary flags.
- **Generation and Playback Programs**:
  - `siggen`: Generates a signal for analysis.
  - `amdemod`: Demodulates the signal and creates an audio signal.
  - `bin2wav`: Translates the audio signal to a WAV file.
  - `analyze_signal`: Looks for information content in the signal.

- **Signal and Filtering Code**:
  - `signal.[ch]`: Loads and stores signal files.
  - `filter.[ch]`: Generates filters and applies them to signals (sequential only).
  - `timing.[ch]`: Measures execution time using various methods.

- **Sequential Version**:
  - `band_scan.c`: Sequential version of the program.

- **Pthread Examples**:
  - `pthread-ex.c`: Demonstrates how to create and use threads on Unix.
  - `parallel-sum-ex.c`: Computes the sum of an array in parallel.

- **Parallelized Program**:
  - `p_band_scan.c`: Your main task is to develop this parallel version, allowing variable processors.

## Usage

Compile the code using `make`. Execute the program as follows:

```bash
Moore> ./p_band_scan text|bin|mmap signal_file Fs filter_order num_bands num_threads num_processors
```

Adjust the number of threads and processors as needed. Ensure the program produces the same output as `band_scan` for proper testing and grading.

## Improving Performance with Parallelization

Now that you've explored scanning for aliens, focus on improving the program's speed. Implement a parallel version of `band_scan` to distribute work among multiple threads and processors.

### Parallel Implementation Usage

```bash
Moore> ./p_band_scan text|bin|mmap signal_file Fs filter_order num_bands num_threads num_processors
```

Ensure the parallel version (`p_band_scan`) produces identical output to the sequential version (`band_scan`) for accurate testing and grading.

## Additional Notes
- Explore different compiler optimizations to enhance the `convolve_and_compute_power()` function.
- Experiment with parallelizing individual convolutions and vectorization using AVX512.
- Consider using OpenMP to parallelize the sequential code in `band_scan.c`.




