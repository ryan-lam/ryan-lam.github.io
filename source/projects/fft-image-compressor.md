---
title: Fast Fourier Transform Image Compressor
date: 2022-08-13 02:43:21
---

## Fast Fourier Transform Image Compressor
> This project was a school assignment and thus I'm unable to release the source code (due to academic honesty/integrity rules)

The Fast Fourier Transform Image Compressor is a project that used Python, NumPy, and Matplotlib to compress images using a Fast Fourier Transform.

The program would be given a 1024x1024 black and white image, which it will then divide into 32x32 pixel sub-blocks. For each sub-block, the program would calculate the Fourier coefficients using NumPy's 2D discrete Fourier Transform ([FFT2](https://numpy.org/doc/stable/reference/generated/numpy.fft.fft2.html)).

Fourier coefficients before compression                     |  Fourier coefficients after compression
:----------------------------------------------------------:|:----------------------------------------------------------:
![](/projects/fft-image-compressor/before-compression.jpg)  |  ![](/projects/fft-image-compressor/after-compression.jpg)

The program would remove the Fourier coefficients that were lower than the user's specified drop tolerance (by setting them to 0). Afterwards, the program would compute the 2D inverse Fourier coefficients ([IFFT2](https://numpy.org/doc/stable/reference/generated/numpy.fft.ifft2.html)) to obtain the resulting compressed 32x32 pixel sub-block. The sub-blocks would be merged together to build the resulting compressed image.

The program also calculated the drop ratio (ratio between the number of changed and non-changed Fourier coefficients).

<div style="text-align:center">
    <p><b>Original Image</b></p>
    <img src="/projects/fft-image-compressor/original.jpg" />
</div>
<br>
<br>

**Compressed Images with Corresponding Drop Ratios**
![](/projects/fft-image-compressor/50.jpg)  |  ![](/projects/fft-image-compressor/70.jpg)
:------------------------------------------:|:------------------------------------------:
![](/projects/fft-image-compressor/89.jpg)  |  ![](/projects/fft-image-compressor/95.jpg)