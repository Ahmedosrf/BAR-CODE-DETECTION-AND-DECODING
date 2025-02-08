# BAR-CODE DETECTION AND DECODING

## Introduction

This project aims to utilize computer vision and image processing techniques to detect and decode barcodes from images. The following methodology outlines the process for processing, enhancing, and extracting barcode information from an input image.

## Methodology

### 1. Image Loading
The input image is loaded using OpenCV as the initial step. The image is read and verified to ensure it has been loaded correctly.

### 2. Grayscale Conversion
The image is converted to grayscale to simplify processing and enhance contrast, facilitating subsequent stages.

### 3. Contrast Enhancement
Histogram equalization is applied to enhance the contrast of the grayscale image, highlighting features of interest, such as the barcode region.

### 4. Noise Reduction
A Gaussian Blur filter is used to smooth the equalized image and reduce noise, improving edge detection accuracy.

### 5. Edge Detection
The Sobel operator detects both horizontal and vertical edges. The gradient magnitude is then calculated to produce a complete edge-detected image.

### 6. Adaptive Thresholding
An adaptive thresholding technique converts the gradient image into a binary format, improving barcode-background separation.

### 7. Morphological Processing
A morphological closure technique is applied to enhance barcode features and eliminate small gaps in detected edges. A rectangular structural element is used to fill tiny gaps and improve connectivity.

### 8. Contour Detection
Contours are detected in the processed image. The largest contour, likely representing the barcode, is identified. The validity of the contour is assessed before further processing.

### 9. Skew Correction
A minimum-area rectangle surrounding the detected contour determines the barcode's orientation. If necessary, an affine transformation is applied to correct the skew and align the barcode horizontally.

### 10. Barcode Extraction
The region of interest (ROI) containing the barcode is cropped from the corrected image. Additional noise reduction and thresholding improve readability.

### 11. Barcode Decoding
The Pyzbar library parses and decodes barcode data from the extracted ROI. If decoding is successful, the retrieved data and barcode type are displayed.

## Conclusion

This methodology presents a structured approach to barcode detection and decoding using image processing techniques. By combining grayscale conversion, contrast enhancement, noise reduction, edge detection, morphological operations, and contour analysis, this method ensures accurate barcode data extraction. The results demonstrate a reliable approach for processing barcode images under various conditions.
