PassportEye documentation
=========================

The PassportEye package provides tools for recognizing machine readable zones (MRZ) from scanned identification documents.
The documents may be located rather arbitrarily on the page - the code tries to find anything resembling a MRZ 
and parse it from there.

Installation
------------

The simplest way to install the package is via ``easy_install`` or
``pip``::

    $ pip install PassportEye

Note that `PassportEye` depends on `numpy`, `scipy`, `matplotlib` and `scikit-image`, among other things. The installation of those requirements, although automatic,
may take time or fail sometimes for various reasons (e.g. lack of necessary libraries). If this happens, consider installing the dependencies explicitly from the binary packages, such as those provided by the OS distribution or the "wheel" packages. Another convenient option is to use a Python distribution with pre-packaged `numpy`/`scipy`/`matplotlib` binaries (Anaconda Python being a great choice at the moment).

In addition, you must have the `Tesseract OCR <https://github.com/tesseract-ocr>`_ installed and added to the system path: the ``tesseract`` tool must be 
accessible at the command line.

Service usage
------------

On launching server/index.py (or using our provided Docker image), PassportEye is going to run as a service on 5000 port, exposing an API that can be used from your services to verify documents. :doc:`The API is documented here <service_usage>`.


Command-line usage
------------------

On installation, the package installs a standalone tool ``mrz`` into your Python scripts path, which can be used from command-line for batch
verification of documents and for other purposes, as necessary. :doc:`The command-line API is described here <command_line_usage>`.

Python usage 
------------

You can also use MRZ as a library in your Python code if you want to be able to integrate it deeper and have better control over features present. :doc:`Python usage is described here <python_usage>`.

.. toctree::
   :maxdepth: 1
   :hidden: 

   usage.rst
   api.rst   
   checks.rst
   scoring.rst   
