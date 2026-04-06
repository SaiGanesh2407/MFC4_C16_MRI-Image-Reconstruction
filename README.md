![Amrita](https://github.com/user-attachments/assets/118097aa-96d2-4724-846c-88a21eb84bf2)

# MFC 4 - 22MAT230

# Sparse Transform and Compressed Sensing Methods to Improve Efficiency and Quality in Magnetic Resonance Medical Imaging

## Team C - 16
### Team Members

| Name | Roll No |
|-----|-----|
| K. Sai Ganesh | CB.SC.U4AIE24226 |
| P. Sathvik | CB.SC.U4AIE24240 |
| Ch. Uday | CB.SC.U4AIE24210 |
| G. Varshini | CB.SC.U4AIE24216 |

### Abstract
This research is about enhancing MRI efficiency through compression and transformation methods like compressed sensing and sparse transform. Traditional MRIs use huge data collection methods resulting in high scan times (up to 30-40 minutes) and high computational costs. To overcome these problems, we have used four reconstruction algorithms namely DWT, FFT, DCT, and Basic Pursuit on undersampled MRI datasets. In the proposed algorithm, random sampling of transform coefficients followed by reconstruction using inverse transformations and optimization is simulated to achieve undersampled data collection for reconstruction purposes. This method will be assessed by the measures of RMSE, PSNR, and SSIM. The results indicate that DCT yields high-quality images with simulation but a reliable reconstruction method that is Basis Pursuit can be considered for further research.

### Introduction
MRI stands for Magnetic Resonance Imaging and is a vital method employed in the field of medicine for examining body organs. Although MRI has some beneficial aspects, it has limitations such as high acquisition time, which can be up to 30-40 minutes.

#### Problem Statement
An MRI image can be reconstructed only when there is a significant amount of k-space data obtained. When there is full data, more scanning time will be needed; conversely, with lesser data, the output image will not be clear.
The objective is to:
Generate a high-quality MRI image by taking less data while reducing the scanning time.

#### Motivation
This study is motivated by the need to apply the concepts of CS in exploiting the sparse nature of images for effective image reconstruction through reduced data.
Comparing different algorithms such as DWT, FFT, DCT, and Basis Pursuit will help find a middle ground for quality image reconstruction in terms of fast and efficient MRI systems.


### Objectives
- Reduce MRI scan time using compressed sensing
- Apply sparsity-based reconstruction techniques
- Compare performance of DWT, FFT, DCT, and Basis Pursuit
- Evaluate reconstruction quality using metrics

### Methodology
MRI acquisition can be modeled as:  

$$
y = F(x)
$$

where:
- x = original image
- F = Fourier transform
- y = measured k-space data

In compressed sensing, the measurement model becomes:

$$
y = \Phi x
$$  

where Φ is the sensing matrix. Since the image is sparse in a transform domain Ψ:

$$
x = \Psi s
$$

then,

$$
y = \Phi \Psi s = \Theta s
$$

Reconstruction is performed by solving the optimization problem:

$$
\min \|s\|_1 \quad \text{subject to} \quad \Theta s = y
$$

This L1-norm minimization ensures sparse recovery of the signal.

#### Algorithm steps
1. Image processing
Here image is changed to grayscale and resized.

$$
A = \frac{A - \min(A)}{\max(A) - \min(A)}
$$ 

2. Sparse Transform Domain Conversion
Three transforms are used:
- DWT (Wavelet Transform) → captures spatial + frequency information
- FFT (Fourier Transform)

$$
F(u,v) = \sum_{x=0}^{M-1} \sum_{y=0}^{N-1} f(x,y)\, e^{-i 2\pi \left(\frac{ux}{M} + \frac{vy}{N}\right)}
$$

- DCT (Cosine Transform) → energy compaction in low frequencies

These transforms convert the image into sparse coefficients.

3. Undersampling  
Random sampling of coefficients:
 N = samplingrate * M
- Only selected coefficients are retained and remaining coefficients are set to zero

4. Reconstruction Algorithms
(a) DWT Reconstruction
- Apply wavelet decomposition
- Randomly sample coefficients
- Reconstruct using inverse wavelet transform

(b) FFT Reconstruction
- Apply FFT
- Randomly sample frequency coefficients
- Reconstruct using inverse FFT:
       X = real(IIFT(y))

(c) DCT Reconstruction
- Apply DCT
- Select largest coefficients
- Reconstruct using inverse DCT

(d) Basis Pursuit (Compressed Sensing)
- Generate random sensing matrix:

$$
y = \Phi x
$$

- Construct sensing matrix:

$$
\Theta = \Phi \Psi^{-1}
$$

- Solve optimization:

$$
\min \|s\|_1 \quad \text{s.t.} \quad \Theta s = y
$$

- Reconstruct image:

$$
x' = \Psi s
$$

### Performance Metrics
Reconstruction quality is evaluated using:
- RMSE(Error):

$$
\text{RMSE} = \sqrt{\frac{1}{N} \sum (x - x')^2}
$$

- PSNR(Quality):

$$
\text{PSNR} = 10 \log_{10} \left( \frac{MAX^2}{MSE} \right)
$$

- SSIM(Similarity):

$$
\text{SSIM} = \frac{(2\mu_x \mu_{x'} + C_1)(2\sigma_{xx'} + C_2)}
{(\mu_x^2 + \mu_{x'}^2 + C_1)(\sigma_x^2 + \sigma_{x'}^2 + C_2)}
$$


### Process flow
<img width="504" height="231" alt="image" src="https://github.com/user-attachments/assets/a821621e-5e4e-4025-9322-4f83acfdf20e" />

### Dataset  
The dataset used in this project consists of MRI brain images collected for medical image processing and reconstruction analysis. It contains approximately 14,715 images representing different brain scans with varying structures and intensity patterns. These images provide sufficient diversity for evaluating reconstruction algorithms under different conditions.
This dataset is suitable for analyzing the performance of compressed sensing techniques, as it allows comparison of reconstruction quality using standard metrics like RMSE, PSNR, and SSIM.

### Conclusion
In this project, we have proposed an efficient methodology for image reconstruction from MRI scans using compressed sensing and sparse transform. The central idea of minimizing the scanning time while ensuring a decent image quality has been successfully achieved through simulation and implementation of DWT, FFT, DCT, and Basis Pursuit methods of reconstruction.
According to our findings, DCT is an efficient method of reconstruction when it comes to simulation, whereas FFT gives better results in line with practical MRI imaging. On the other hand, Basis Pursuit algorithm based on L1-norm proves to be more efficient and reliable for handling undersampling problems.
Thus, we can conclude that there is always a trade-off between image quality and computational complexity, and the proposed technique helps minimize these limitations and improve efficiency in terms of reduced amount of data.

### Results
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

### Future Work
- Implement deep learning-based reconstruction
- Improve reconstruction speed
- Use real-time MRI datasets

### References
1. S. Villota and E. Inga, “Sparse Transform and Compressed Sensing Methods to Improve Efficiency and Quality in Magnetic Resonance Medical Imaging,” Sensors, vol. 25, no. 5137, 2025.
2. Dataset - https://www.kaggle.com/datasets/ashfakyeafi/brain-mri-images
3. D. L. Donoho, “Compressed Sensing,” IEEE Transactions on Information Theory, vol. 52, no. 4, pp. 1289–1306, 2006.
4. M. Lustig, D. Donoho, and J. M. Pauly, “Sparse MRI: The Application of Compressed Sensing for Rapid MR Imaging,” Magnetic Resonance in Medicine, 2007.

### Update 1
1. Changing code from Python to Matlab.
2. Run algorithms for more images(only 1 image used with 3 sampling rate) and compare the average
performance to conclude.
3. Toy example to compare the algorithms.

### Update 2
1. How are PSNR, RMSE, SSIM values are computed.
2. Implement both random sampling and sorted sampling for every algorithm.

### Additional Information
Platform used:- Laptop / Matlab 2024b  
Hardware: CPU  
Time taken: 2793.38 seconds  
MATLAB 2024b  

