.. _python_usage:
Command-line usage
==================

In command-line, running:

    $ mrz <filename>
    
will process a given filename, extracting the MRZ information it finds and printing it out in tabular form.
Running ``mrz --json <filename>`` will output the same information in JSON. Running ``mrz --save-roi <roi.png>`` will,
in addition, extract the detected MRZ ("region of interest") into a separate png file for further exploration.
Note that the tool provides a limited support for PDF files -- it attempts to extract the first DCT-encoded image 
from the PDF and applies the recognition on it. This seems to work fine with most scanner-produced one-page PDFs, but
has not been tested extensively.

After getting a response, :doc:`refer to our response description <passporteye_response>`.