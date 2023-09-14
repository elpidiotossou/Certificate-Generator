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
3. Run the `Jpeg_to_PDF.ipynb` notebook to combine the certificates into a PDF:

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

