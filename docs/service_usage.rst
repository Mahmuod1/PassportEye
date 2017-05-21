.. _service_usage:

Service usage
=============

Uploading files to PassportEye through API is simple. For example, here's Python code 
you can use to do that:

.. code-block:: python

    >>> import requests
    >>> print("ok")
    >>> files = {'file': open('passport_scan.jpg', 'rb')}
    
    >>> r = requests.post("http://passporteye.domain/upload_file", 
    >>> r.text
	
After getting a response, :doc:`refer to our response description <api>`.

