.. _python_usage:

Python usage
============

In order to use the PasswordEye functions in Python code, simply do:

    >> from passporteye import read_mrz
    >> mrz = read_mrz(image_filename)

The returned object (unless it is None, which means no ROI was detected) contains the fields extracted from the MRZ along
with some metainformation. For the description of the available fields, see the docstring for the `passporteye.mrz.text.MRZ` class.
Note that you can convert the object to a dictionary using the ``to_dict()`` method.

If you want to have the ROI reported alongside the MRZ, call the ``read_mrz`` function as follows::

    >> mrz = read_mrz(image_filename, save_roi=True)

The ROI can then be accessed as ``mrz.aux['roi']`` -- it is a numpy ndarray, representing the (grayscale) image region where the OCR was applied.

For more flexibility, you may instead use a ``MRZPipeline`` object, which will provide you access to all intermediate computations as follows::

    >> from passporteye.mrz.image import MRZPipeline
    >> p = MRZPipeline(filename)
    >> mrz = p.result

The "pipeline" object stores the intermediate computations in its ``data`` dictionary. Although you need to understand the underlying algorithm
to make sense of it, sometimes it may provide for insightful visualizations. This code, for example, will plot the binarized version of the original image
which is used in the algorithm to extract ROIs alongside the boxes corresponding to the extracted ROIs::

    >> imshow(p['img_binary'])
    >> for b in p['boxes']:
    ..     plot(b.points[:,1], b.points[:,0], c='b')
    ..     b.plot()
	
After getting a response, :doc:`refer to our response description <api>`.
