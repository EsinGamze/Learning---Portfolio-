# 🌍 Image Quality Evaluation – Simulated and Real Satellite Imagery

This project presents a series of image quality analyses conducted on:
1. A publicly available image of Earth from NASA (Blue Marble dataset)
2. Real Sentinel-2 satellite imagery over Berlin

It demonstrates how key image quality metrics respond to **simulated blur** and **real atmospheric effects** such as cloud cover.

---

## 🛰️ Dataset 1 – NASA Blue Marble (Simulated Blur)

- **Source**: [NASA Visible Earth - Blue Marble (December 2004)](https://visibleearth.nasa.gov/images/73909/december-blue-marble-next-generation-w-topography-and-bathymetry/73911l)  
- **Filename**: `world.jpg`

### ✅ Performed Analyses:
- Gaussian blur simulation at varying levels  
- Histogram analysis  
- Laplacian-based sharpness metric  
- Contrast via standard deviation  
- Canny edge detection  
- Frequency analysis (FFT)  
- PSNR & SSIM similarity measures  
- Sharpness vs blur sensitivity curve

---

## 🌐 Dataset 2 – Sentinel-2 Imagery (Berlin)

Two Level-2A Sentinel-2 RGB images were downloaded from the Copernicus Data Space and exported from QGIS:

- `sentinel2-withoutcloud.jpg` → Cloud-free  
- `sentinel2-cloudy.jpg` → Cloud-covered version of the same area

### ✅ Performed Analyses:
- Sharpness & contrast comparison  
- Histogram distribution  
- Canny edge detection  
- FFT-based frequency comparison  
- PSNR & SSIM similarity evaluation  
- Sharpness vs simulated blur comparison  
- Summary of metrics in CSV

---

## 📊 Quality Metrics Summary (Sentinel-2)

| Metric                  | Without Clouds | Cloudy Scene |
|-------------------------|----------------|---------------|
| Sharpness (Laplacian)   | ...            | ...           |
| Contrast (Std Dev)      | ...            | ...           |
| SSIM                    | 1.0            | ...           |
| PSNR (dB)               | ...            | ...           |

*See `iq_metrics_summary.csv` for full results.*


---

## 📁 Project Structure

```
Learning---Portfolio-/
└── Python/
    └── Image-Processing/
        ├── image_process.ipynb
        ├── [input & output image files]
        ├── [plots and metric charts]
        └── iq_metrics_summary.csv
```


---

## 📁 Key Output Files

To clarify which files belong to which dataset, output filenames are grouped below:

### 🛰️ NASA Blue Marble (Simulated Blur)
- `original_image.jpg`
- `blurred_image.jpg`
- `original_histogram.png`
- `blurred_histogram.png`
- `comparison_original_vs_blurred.png`
- `canny_edge_comparison_world.png`
- `sharpness_bar_chart_world.png`
- `contrast_bar_chart_world.png`
- `fft_original.png`
- `fft_blurred.png`
- `sharpness_vs_blur_curve_world.png`

### 🌐 Sentinel-2 (Real Satellite Imagery – Berlin)
- `sentinel2-withoutcloud.jpg`
- `sentinel2-cloudy.jpg`
- `histogram_clear.png`
- `histogram_cloudy.png`
- `sharpness_bar_chart_sentinel.png`
- `contrast_bar_chart_sentinel.png`
- `canny_edges_comparison_sentinel.png`
- `fft_clear.png`
- `fft_cloudy.png`
- `sharpness_vs_blur_curve_sentinel.png`
- `iq_metrics_summary.csv`


---

## 📦 Requirements

Install the required Python libraries using pip:

```bash
pip install opencv-python numpy matplotlib scikit-image pandas

