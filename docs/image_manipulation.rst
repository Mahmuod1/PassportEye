.. _image_manipulation:

Image manipulation detection
============================

PassportEye employs the most efficient image manipulation detection techniques that cover 99.5% of 
all artificially-crafted and digitally-manipulated images. The checks listed all notify the platform
about possible document falsification.


* **Verification of fonts** used on the documents, using a database of known fonts used in 
  identification documents worldwide, as well as optionally using an external neural network trained 
  on distinguishing between different fonts.

* Check for **photo presence** on the identification document. The check uses a neural network TODO: ask Christian to elaborate

* Check for **possible digital manipulation** in JPEG documents, employing Error Level Analysis. 
  The ELA check detects whether the provided image has been edited by image manipulation programs, 
  specifically, if regions of the image have changed considerably compared to other regions. The 
  check is based on the fact that editing the image requires re-compressing the edited parts, thus
  changing the statistical distribution of compression artifacts. The Error Level Analysis check
  implementation uses convolutional neural networks to ensure robustness and reduce false negative rate, 
  as opposed to more popular algorithms using geometrical and statistical features that tend to have
  high error margin in edge cases.
  Therefore, the PassportEye ELA check has a high weight in calculating the overall trust score.
