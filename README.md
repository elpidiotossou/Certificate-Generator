# Certificate-Generator

This repository contains Jupyter Notebook scripts to assist in certificate generation, identify the placement of names on certificates and convert the certificates to pdf.

## Certificate Generator

The `certificate_generator.ipynb` Jupyter Notebook helps generate customized certificates by overlaying text on a template image. Customize fonts, text colors, and positions using data from a CSV file.

### Usage

1. Replace the template image, CSV file, and font file paths in the notebook.
2. Customize text, fonts, and positions.
3. Run the notebook cells to generate certificates.

## Name Placement Indicator

The `name_placement_indicator.ipynb` Jupyter Notebook provides an interactive widget to identify where names should be placed on a certificate template image.

### Usage

1. Replace the path to your certificate template image in the notebook.
2. Run the notebook cells to open the interactive widget.
3. Use sliders to pinpoint name placement coordinates.

## Combining Certificates into a PDF

After generating individual certificate images, you can combine them into a single PDF file using the provided Python script. Follow these steps:

1. Generate individual certificate images using the `certificate_generator.ipynb` notebook.
2. Ensure the generated JPG images are saved in a directory.
3. Run the following Python script to combine the certificates into a PDF:
```python
from fpdf import FPDF
import os

# Directory containing the JPG images
png_output_dir = 'path_to_directory_containing_JPG_images'

# Output path for the combined PDF
pdf_output_path = 'path_to_combined_pdf_output.pdf'

# Create a PDF object with landscape A4 dimensions
pdf = FPDF(orientation='L', unit='mm', format='A4')

# Loop through each JPG image in the directory
for filename in os.listdir(png_output_dir):
    if filename.endswith('.jpg'):
        image_path = os.path.join(png_output_dir, filename)
        
        # Add a page to the PDF with landscape A4 dimensions
        pdf.add_page()
        
        # Set the image as the background for the page
        pdf.image(image_path, x=0, y=0, w=297, h=210)  # Landscape A4 dimensions

# Save the combined PDF
pdf.output(pdf_output_path)
print(f"Combined PDF saved as {pdf_output_path}.")

## Requirements

- Jupyter Notebook
- Python 3.x
- Pillow (PIL) library
- Matplotlib
- ipywidgets
- fpdf library

## Getting Started

1. Clone this repository to your local machine.

```bash
git clone https://github.com/elpidiotossou/Certificate-Generator.git

