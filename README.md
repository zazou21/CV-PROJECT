#  Barcode Image Restoration & Decoding

This project explores multiple signal and image processing techniques to **restore and decode barcodes** that are affected by noise, rotation, disconnection, or distortion. It focuses on frequency domain filtering, morphological operations, and intelligent heuristics for evaluating barcode quality — ultimately enabling reliable decoding of noisy barcode images.

---

##  Project Goals

-  **Remove periodic noise**, salt & pepper noise, and blur from barcode images.
-  **Correct misaligned barcodes** by detecting their dominant orientation and rotating them.
-  **Connect broken barcode bars** and fill in missing regions.
-  **Evaluate barcode quality** using frequency domain analysis and histogram-based heuristics.
-  **Decode Code 11 barcodes** with tolerance to slight distortion.

---

##  Main Techniques Used

###  Frequency Domain Processing
- **Sinc pattern analysis**: Used to distinguish clean barcodes from corrupted ones.
- **Custom masking** in the Fourier domain to suppress undesired frequencies (horizontal/vertical).
- **Detection of periodic noise** by analyzing peak locations off the central sinc.

###  Image Restoration
- **Hough Line Transform** to detect angles and correct image rotation.
- **Morphological Closing** to connect disconnected vertical bars.
- **Flood Fill & Contour Filling** to clean up barcode shapes.

###  Quality Assessment
- **Histogram-based brightness/darkness/contrast checks**
- **Laplacian variance** for blur detection
- **Peak ratio check** for periodic noise verification

###  Barcode Decoding
- Tolerant Code 11 decoder supporting ±1 variation in bar widths.
- Custom narrow/wide bar parsing from column-wise pixel intensity patterns.

---

##  Sample Flow

1. **Load image**
2. **Check for noise/rotation**
3. **Apply appropriate filtering (frequency or morphological)**
4. **Rotate and crop barcode**
5. **Enhance vertical bars**
6. **Decode barcode**

---

