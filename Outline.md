This is a “work in progress” workshop in which we will discuss some approaches and related software we are developing for extracting information from text documents such as scanned documents with Optical Character Recognition, and PDF, DOCX files.  This includes finding information such as tables, images, lists, sections and section titles, bibliographic information, author affiliations, …  We’ll also discuss the software development process for this task.  This is intended as a brainstorming session and also to get people started with working on different types of non-standard text formats.


?HTML documents?

+ Scanned Documents
  + OCR
     + tesseract  (Rtesseract)
     + PDFPenPro
     + Abbyy  (abbyR)

  + Conversion to 
     + text
     + docx
     + XML with fine-grained information about location on page.

+ Abbyy, PDFPenPro - commercial
+ tesseract - open source

+ http://tabula.technology/
+ pdftohtml, poppler
+ pdf2txt.py

+ PDF
   + Convert to text, XML, Docx


# 3 Different Levels

1. Raw, simple text - e.g., pdf2text, tesseract command line.
1. Docx - medium-level structure. Need to access the content and piece it together.
1. XML - (pdftohtml -xml)


+ Reconstruct   

+ Multiple columns
+ Connecting text, tables, ... across pages


# Structure of PDF Documents
These are complex, very expressive beasts.



# Structure of DOCX Documents
These are zip files - a collection of files.
These files define different elements of a document.

# Structure of HTML Documents
These are not really that mysterious.
We have <table>, <ol>, <ul>, <h1>...<h6> elements and so on.
We use XPath or some other selector mechanism.

readHTMLTable() does reasonably well for many documents.
It doesn't handle everything.
Use XPath for more control.
Examples of complicated cases include
+ content spanning multiple cells, either horizontally or vertically, i.e. spanning
multiple columns.


# OCR with (R)Tesseract

## Line detection.
## Specifying Dictionaries
## Fixing recognition by context.






# ImageMagick

Take a scanned PDF document, and break it into pages.
Can do this on OSX with Automator, or generally with ImageMagick's
command line tool convert:
```
convert -density 150 -antialias "Lundkvist-1992-Bank vole monoclonal antibodies.pdf" -resize 1024x -quality 100 "bob%03d.jpg"
```

Then we can OCR each of these pages.

Alternatively, we load the PDF into PDFPenPro and have it convert it for us.




## ImageMagick

You can check which delegates are enabled with
```
convert -list configure | grep DELEGATES
```

Install libjpeg,libpng, zlib, etc. before installing so that these are enabled for the  DELEGATES
Otherwise, convert may not be able to deal with some images in the PDFs.
Should see the DELEGATES at the end of the configuration. Check, e.g.
```
    DELEGATES       = bzlib mpeg jng jpeg lzma png ps tiff x xml zlib
```

See http://www.imagemagick.org/discourse-server/viewtopic.php?t=12366
