#BOEM Research Program - OCR Data Processing

Overview

This project is part of the BOEM (Bureau of Ocean Energy Management) research program and includes a Python script (main.py) designed to process scanned well reports, extract relevant data using Optical Character Recognition (OCR), and generate structured output in CSV format. The script applies various image processing techniques to improve text extraction accuracy and analyzes the data to produce meaningful insights.

Purpose

The primary goal of this script is to automate the extraction of structured metadata from legacy well reports, helping researchers efficiently analyze oceanic drilling data. It employs Tesseract OCR along with pre-trained models to recognize key information, improving accuracy through image preprocessing techniques.

How It Works

Image Preprocessing:

- The script reads image files (.jpg) from the final_deliverable/img directory.
- It converts images to grayscale and applies thresholding techniques to enhance text clarity.
- Processed images are temporarily stored before OCR extraction.

OCR Processing:

- Tesseract OCR is used with a custom-trained model (eng_final_model) to extract text from the images.
- Extracted text is saved into individual .txt files within the final_deliverable/txts directory.

Data Structuring and Output:

- The script processes OCR-extracted text to identify structured fields such as time, date, elapsed time, temperature, and pressure values.
- Extracted data is compiled into a Pandas DataFrame and saved as CSV files in the final_deliverable/csv directory.

Accuracy Evaluation:

- The script includes a function to evaluate keyword detection accuracy based on predefined expected terms.
- A summary of accuracy is printed to help validate OCR results.

Dependencies

Ensure you have the following dependencies installed before running the script:

- Python 3.x
- OpenCV (cv2)
- PIL (Pillow)
- pytesseract
- pandas
- matplotlib

Usage

1. Place input images in final_deliverable/img.
2. Run the script:
   ```
   python main.py
   ```
3. Extracted text files will be saved in final_deliverable/txts, and structured data will be stored as CSV files in final_deliverable/csv.

Notes

- Ensure that Tesseract OCR is installed and correctly configured. Update the pytesseract.pytesseract.tesseract_cmd path in the script if necessary.
- The OCR model used (eng_final_model) should be pre-trained for optimal accuracy.

This script enhances data extraction from historical well reports, aiding in oceanic research efforts by converting unstructured reports into structured datasets for further analysis.
