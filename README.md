# SETI Lab

## Overview

Welcome to the SETI Lab, where we embark on a quest to discover extraterrestrial intelligence through radio wave analysis. In this project, we optimize signal processing code using parallelization techniques, SIMD vector instructions, and compiler optimizations to achieve a remarkable 60x speed-up in processing.

## Lab Description

The Search for Extraterrestrial Intelligence (SETI) involves analyzing signals captured by radio telescopes to identify potential signs of alien civilizations. Our focus is on optimizing the computational process to enhance the efficiency of signal processing.

The primary goals of the lab include fostering an understanding of parallel algorithms, providing exposure to low-level parallel programming using pthreads, and exploring the impact of compiler optimizations.

## Optimizations

We've implemented optimizations such as `p_band_scan` and `p_convolve_and_compute_power` to significantly improve program performance. These optimizations involve parallelizing the code using POSIX thread libraries, AVX-512 SIMD vector instructions, and the OpenMP API.

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
  - `filter.[ch]`: Generates filters and applies them to signals (modified to be parallelized).
  - `timing.[ch]`: Measures execution time using various methods.

- **Sequential Version**:
  - `band_scan.c`: Sequential version of the program.

- **Pthread Examples**:
  - `pthread-ex.c`: Demonstrates how to create and use threads on Unix.
  - `parallel-sum-ex.c`: Computes the sum of an array in parallel.

- **Parallelized Program**:
  - `p_band_scan.c`: The parallelized version of the program `band_scan.c`.

## Usage

Compile the code using `make`. Execute the program as follows:

```bash
$ ./p_band_scan text|bin|mmap signal_file Fs filter_order num_bands num_threads num_processors
```

Adjust the number of threads and processors as needed.

___

May your code search the cosmos for signs of extraterrestrial intelligence! 🌌👽



