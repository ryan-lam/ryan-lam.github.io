---
title: Fast Fourier Transform Audio Filter
date: 2022-08-22 00:00:01
---

## Fast Fourier Transform Audio Filter
> This project was a school assignment and thus I'm unable to release the source code (due to academic honesty/integrity rules)

The Fast Fourier Transform Image Compressor is a project that used Python, NumPy, and Matplotlib to differentiate the high and low frequencies of a given audio signal which resulted in a low-pass and high-pass filter.

<div style="text-align:center">
    <img src="/projects/fft-audio-filter/original.jpg" width="400"/>
</div>

The program would be given a noisy audio signal comprised of high and low frequencies, compute the Fourier coefficients ([FFT](https://numpy.org/doc/stable/reference/generated/numpy.fft.fft.html)) for the audio signal using NumPy, and use the Fourier coefficients power spectrum of the audio signal.

<div style="text-align:center">
    <img src="/projects/fft-audio-filter/original-power-spectrum.jpg" width="400"/>
</div>

As shown in the power spectrum above, there are points where the magnitude of the Fourier coefficients would spike. Using these spikes, the program can differentiate the high and low frequencies in the audio signal. Using a given tolerance from the user, the program would compare the coefficients in the power spectrum to the given tolerance. 

If the coefficient was lower than the tolerance, the program would "keep" the coefficient. If the coefficient was higher than the tolerance, the program would discard the coefficient by setting it to 0. The resulting coefficients would represent the isolated high frequencies. The program would calculate the inverse Fourier coefficients ([IFFT](https://numpy.org/doc/stable/reference/generated/numpy.fft.ifft.html)) on the isolated high frequencies to obtain the filtered (high pitch/frequency) audio signal.

The inverse comparison operator would be used to isolate the lower frequencies.

Isolated High Frequency Audio Signal (Bird Chrips)          |  Respective Power Spectrum of Audio Signal
:----------------------------------------------------------:|:----------------------------------------------------------:
![](/projects/fft-audio-filter/bird.jpg)                    |  ![](/projects/fft-audio-filter/bird-power-spectrum.jpg)

Isolated Low Frequency Audio Signal (Train Whistle)         |  Respective Power Spectrum of Audio Signal
:----------------------------------------------------------:|:----------------------------------------------------------:
![](/projects/fft-audio-filter/train.jpg)                   |  ![](/projects/fft-audio-filter/train-power-spectrum.jpg)
