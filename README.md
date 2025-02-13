# Amazon ML Challenge - Feature Extraction from Images

## Team: Enigma Learners

### Rank Achieved: 191

### Accuracy Score: 0.46215635

---

## Problem Statement

The objective of this challenge was to extract specific product-related features from images provided in the dataset. The extracted features included attributes such as `item_weight`, `item_volume`, and similar entity values.

---

## Data Description

The dataset consists of the following columns:

- **index**: A unique identifier (ID) for the data sample.
- **image\_link**: Public URL where the product image is available for download.
  - Example: `https://m.media-amazon.com/images/I/71XfHPR36-L.jpg`
  - Images can be downloaded using the `download_images` function from `src/utils.py`.
- **group\_id**: Category code of the product.
- **entity\_name**: Name of the feature to be extracted (e.g., `item_weight`).
- **entity\_value**: The actual feature value (e.g., `34 gram`).
  - Note: In `test.csv`, the `entity_value` column is missing as it is the target variable.

---

## Project Structure

```
├── Ocr_text_extraction.ipynb        # Notebook for OCR-based text extraction
├── README.md                        # Project documentation
├── amazon_ml_prediction (1).ipynb   # Notebook for ML model prediction
├── combined (1).csv                 # Combined dataset
├── test_prediction (1).csv          # Final test predictions
```

---

## Solution Approach

Our approach primarily relied on **Regular Expressions (RegEx)** to extract entity values from image metadata and filenames. The key steps involved:

1. **Data Preprocessing**
   - Downloaded images using `download_images` function.
   - Extracted relevant text from metadata.
2. **Feature Extraction using RegEx**
   - Designed regex patterns to extract numeric values associated with entity names.
   - Applied regex parsing to text extracted from images.
3. **Model Training & Evaluation**
   - Used simple pattern matching techniques for entity value extraction.
   - Evaluated performance based on F1-score.

---

## Implementation Details

- The **regex-based extraction** method efficiently extracted numerical values and units.
- Python libraries used:
  - `re` (Regular Expressions for pattern matching)
  - `pandas` (Data processing)
  - `requests` (Downloading images)
  - `PIL` (Image processing)
- Code structure:
  - `src/utils.py` → Contains helper functions for image downloading & processing.
  - `src/test.ipynb` → Sample code for extracting features.
  - `main.py` → End-to-end pipeline for model execution.

---

## Results & Performance

- Final Accuracy Score: **0.46215635**
- Final Rank: **191**
- Key Findings:
  - Regex was effective for extracting simple numerical values.
  - Accuracy could be improved by integrating **OCR-based techniques** (e.g., Tesseract, EasyOCR).
  - Further model training with **Deep Learning-based Image Processing** could enhance feature extraction.

---

## Future Improvements

To improve performance, the following approaches can be considered:

- **Optical Character Recognition (OCR)**
  - Using Tesseract, EasyOCR, or Google Vision API for better text extraction from images.
- **Deep Learning-Based Feature Extraction**
  - Training CNN models like ResNet or EfficientNet to identify relevant regions in images.
- **Hybrid Approach**
  - Combining regex-based extraction with an ML-based classification model.

---

## How to Run the Project

1. Clone the repository:
   ```sh
   git clone <repo-link>
   cd <repo-folder>
   ```
2. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
3. Download images using the `download_images` function in `src/utils.py`.
4. Run the main extraction pipeline:
   ```sh
   python main.py
   ```
5. Generate predictions and save the output CSV in the required format.

---

## Contributors

- **Rishikesh Nandan**
- **Team: Enigma Learners**


---

