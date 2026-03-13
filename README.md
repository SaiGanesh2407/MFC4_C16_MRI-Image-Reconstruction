# Sparse Transform and Compressed Sensing Methods to Improve Efficiency and Quality in Magnetic Resonance Medical Imaging

## Team C - 16
### Team Members

| Name | Roll No |
|-----|-----|
| K. Sai Ganesh | CB.SC.U4AIE24226 |
| P. Sathvik | CB.SC.U4AIE24240 |
| Ch. Uday | CB.SC.U4AIE24210 |
| G. Varshini | CB.SC.U4AIE24216 |

### Outline
This project aims to reduce MRI scan time while maintaining good image quality using compressed sensing.
MRI images are reconstructed from fewer samples using transforms like FFT, DWT, DCT and Basis pursuit.
The reconstructed images are compared using quality measures such as PSNR, RMSE, and SSIM.
The goal is to find a balance between fast reconstruction and accurate image quality.

### Update 1
1. Changing code from Python to Matlab.
2. Run algorithms for more images(only 1 image used with 3 sampling rate) and compare the average
performance to conclude.
3. Toy example to compare the algorithms.

### Update 2
1. How are PSNR, RMSE, SSIM values are computed.
2. Implement both random sampling and sorted sampling for every algorithm.

## Process flow
<img width="504" height="231" alt="image" src="https://github.com/user-attachments/assets/a821621e-5e4e-4025-9322-4f83acfdf20e" />

## Results
<img width="1800" height="1300" alt="image" src="https://github.com/user-attachments/assets/b4495b8b-fff6-4003-b718-c022d6f7b05c" />

<img width="1800" height="1300" alt="image" src="https://github.com/user-attachments/assets/d2206eb1-f7ca-4aee-9be8-16fa3abb3517" />

<img width="1800" height="1300" alt="image" src="https://github.com/user-attachments/assets/d9a3e841-1d44-437f-b430-91a00ffdb2ad" />

<img width="600" height="500" alt="image" src="https://github.com/user-attachments/assets/3b9adda4-7c31-4f4d-aab5-8b2e4b7080fe" />

## Result Summary

| Method | PSNR (dB) | RMSE | SSIM |
|------|------|------|------|
| DWT Random | 15.6729 | 0.1673 | 0.3516 |
| FFT Random | 17.3351 | 0.1397 | 0.3488 |
| DCT Random | 18.3196 | 0.1335 | 0.3738 |
| L1 Random | 28.4911 | 0.0406 | 0.7177 |
| DWT Sorted | 42.4213 | 0.0103 | 0.9662 |
| FFT Sorted | 41.2067 | 0.0099 | 0.9700 |
| DCT Sorted | 44.2179 | 0.0074 | 0.9796 |
| L1 Sorted | 27.3274 | 0.0516 | 0.6031 |

### Additional Information
Platform used:- Laptop / Matlab 2024b  
Hardware: CPU  
Time taken: 2793.38 seconds  
MATLAB 2024b  
