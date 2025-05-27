#  Image Quality Analysis Report

This report documents the results of two image quality analysis experiments:

1. **Simulated blur on a global Earth image** (NASA Blue Marble)
2. **Real atmospheric interference** (cloud cover) on Sentinel-2 satellite imagery

Our goal is to evaluate how standard image quality metrics (sharpness, contrast, SSIM, PSNR, histogram distribution, FFT spectrum, and Canny edges) respond to visual degradation.

---

##  Part I: Simulated Blur on Earth Image

###  Image Used

* NASA Blue Marble (December 2004), downsampled RGB version
* Converted to grayscale for analysis

###  Processing Steps

* Applied Gaussian blur (kernel size 11x11)
* Compared original vs blurred image using multiple techniques

###  Key Observations

**1. Sharpness (Laplacian Variance)**

* Original: **630.13**
* Blurred: **4.04**

> Huge drop confirms the Laplacian method is highly sensitive to blur.

**2. Contrast (Standard Deviation)**

* Original: **81.93**
* Blurred: **80.87**

> Slight decrease, indicating a minor flattening in brightness range.

**3. SSIM (Structural Similarity)**

* Score: **0.8682**

> Shows moderately high similarity, but reduced structure integrity.

**4. PSNR (Peak Signal-to-Noise Ratio)**

* Score: **35.64 dB**

> Indicates reasonably preserved pixel values despite visible blurring.

**5. Canny Edge Detection**

* The original contains detailed edges across continents.
* The blurred version shows significant loss of detail.

**6. FFT Spectrum**

* High frequencies are suppressed in the blurred image.
* Low-frequency dominance increases, indicating loss of fine texture.

**7. Sharpness vs Blur Curve**

* Clear exponential decay in sharpness as blur kernel size increases.
* Confirms Laplacian variance as a reliable sharpness measure.

###  Summary

Blur drastically reduces sharpness and weakens structural cues, but contrast and pixel-wise similarity remain reasonably stable. FFT and edge detection reveal underlying detail loss more clearly than contrast or PSNR.

---

##  Part II: Real Atmospheric Effects (Sentinel-2)

###  Dataset Description

* Two L2A RGB exports from the Copernicus Sentinel Hub (via QGIS)
* Location: Berlin region
* Format: 8-bit JPEG
* Cloud-free vs cloud-covered version

###  Key Observations

**1. Sharpness (Laplacian Variance)**

* Without Clouds: **419.34**
* Cloudy: **452.40**

> Contrary to expectation, the cloudy image had a slightly **higher** sharpness score. This may be due to high-frequency noise introduced by bright cloud edges.

**2. Contrast (Standard Deviation)**

* Without Clouds: **97.81**
* Cloudy: **100.30**

> Slight increase in contrast in cloudy image, likely from bright cloud pixels.

**3. SSIM**

* Score: **0.7855**

> Indicates structural deviation due to cloud coverage

**4. PSNR**

* Score: **33.24 dB**

> Shows measurable pixel-level difference introduced by clouds

**5. Canny Edge Detection**

* Cloud-free: regular features and boundaries are visible
* Cloudy: additional noisy edges from clouds obscure terrain

**6. FFT Spectrum**

* Both images show typical frequency patterns
* Slight noise amplification is visible in the cloudy spectrum

**7. Sharpness vs Blur Curve (Cloud-free image)**

* Sharpness declines consistently with increased blur kernel size

###  Summary

Atmospheric effects like cloud cover create brightness and contrast anomalies that **do not always reduce sharpness scores** due to noise contribution. This emphasizes the need to **analyze multiple metrics together**, not in isolation.

---

##  Future Directions

* Include other degradations (noise, haze, temporal change)
* Use region-based SSIM for local analysis
* Perform classification or cloud detection pre-processing

---

##  Final Remarks

This study demonstrates how quantitative metrics react to both simulated and real-world degradation. While some metrics (e.g., sharpness) are highly sensitive to blur, **edge detection and FFT** provide better spatial understanding. **Cloud interference does not behave like blur**, which calls for a more nuanced approach to satellite image quality assessment.
