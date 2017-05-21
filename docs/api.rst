PassportEye API documentation!
==============================

Uploading files to PassportEye is simple. For example, here's Python code 
you can use to do that:

.. code-block:: python

    >>> import requests
    >>> print("ok")
    >>> files = {'file': open('passport_scan.jpg', 'rb')}
    
    >>> r = requests.post("http://passporteye.domain/upload_file", 
    >>> r.text

Example response:

.. include:: example.json
    :code: json



.. toctree::
   :maxdepth: 2
   :caption: Contents:
