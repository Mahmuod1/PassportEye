.. _mrz_algorithm:
MRZ verification
================

MRZ - machine-readable zone

PassportEye uses Machine-Readable Zones (further: MRZ) to check for the markers
of document falsification. 

# Example MRZ on document

As MRZ encodes all the human-readable data present on identification documents, it's trivial
for a computer to compare MRZ data to data that's written in human-readable form on the
document, notifying about possible inconsistencies and calculating the error score 

PassportEye implements MRZ manipulation interface which internally conforms to the 
ICAO Document 9303 (endorsed as ISO/IEC 7501-1). The library is capable of:

* Decoding MRZ 

* Detecting MRZ type

* Decoding 
