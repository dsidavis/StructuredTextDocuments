# OCR
Rtesseract
tesseract

## Commercial
### Abbyy API
+ Online/cloud
+ 100 free per month
+ Pay for additional documents
+ Output in XML, Docx, txt, ...
   + Pay for conversion, get any number of formats.
+ R package - abbyyR
+ Python - SDK utilities process.py

+ PDFPenPro
  + Applescript code: Github.com  dsidavis/PDF2Docx.git


# Word files

+ RWordXML
    + ROOXML, Rcompression, XML
+ docxtractr


# PDF
+ pdftohtml - convert PDF to XML/HTML/...
+ ReadPDF - reads XML output from pdftohtml
+ Rpoppler
    + High-level interface to libpoppler, similar to C++ code in pdftohtml
+ Rrawpoppler - low-level, customizable framework for using libpoppler with R functions.
   

## Other PDF Reading tools.
+ pdf2txt.py
+ pdfminer


## HTML

# Spell Checking
+ Useful when checking results of OCR and looking for alternatives.
   + tesseract provides alternatives
   + spell checker uses different approach
+ Aspell package 
+ utils::aspell() function


## Image Processing
+ Rtesseract (leptonica functions)
+ jpeg, png, tiff - manipulate the image directly (as array)
+ imager
+ C++ - OpenCV
  + 

