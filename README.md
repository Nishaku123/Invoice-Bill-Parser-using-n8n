# n8n Bill Parser Workflow (OCR Automation)

This n8n workflow automates bill processing using OCR. It monitors a **Google Drive folder**, detects file types (PDF or image), extracts relevant bill data using **Mistral AI OCR**, appends structured information to Google Sheets, and moves processed files to a separate folder.

## Workflow Overview

1. **Google Drive Trigger**  
   - Watches the **"To Be Processed"** folder for any new or updated files.

2. **File Type Check**  
   - Uses an `If/Else` node to determine whether the file is a PDF, image, or unsupported type.

3. **OCR Processing (Mistral AI)**  
   - Eligible files are sent to **Mistral AI OCR** for text extraction.

4. **Information Extraction**  
   - Parses the OCR output to extract key bill details:
     - Invoice Number
     - Invoice Date
     - Vendor Name
     - Amount

5. **Google Sheets Append**  
   - Adds extracted data to a designated Google Sheet for record keeping.

6. **Move Processed Files**  
   - Moves successfully processed files from **"To Be Processed"** to **"Processed"** folder in Google Drive.

---

## Requirements

- n8n instance (local or cloud)  
- Google Drive credentials  
- Google Sheets credentials  
- Mistral AI API key for OCR processing  

---

## Usage

1. Import the workflow JSON into your n8n instance.  
2. Configure credentials for Google Drive, Google Sheets, and Mistral AI.  
3. Activate the workflow.  
4. Place bills (PDF or image) in the **"To Be Processed"** folder in Google Drive.  
5. The workflow automatically extracts data, updates Google Sheets, and moves the file to the **"Processed"** folder.

---

## Notes

- Ensure the folder paths match the workflow triggers.  
- Only PDFs and supported image formats are processed.  
- Processing time depends on file size and Mistral AI API limits.  
- This workflow focuses on **OCR-based information extraction** and automated logging.

---

## Repository Structure
