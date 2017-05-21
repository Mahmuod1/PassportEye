.. _scoring:
How PasswordEye calculates trust score
======================================

PassportEye uses multiple factors in calculating the total score, including MRZ verification score, EXIF legitimacy score, 

* MRZ score
  * Compares birth date checksum in MRZ to the calculated checksum - 15/100 points
  * Compares personal number checksum in MRZ to the calculated checksum - 15/100 points
  * Compares expiration date checksum in MRZ to the calculated checksum - 15/100 points
  * Sanity-checks name length - 10/100 points
  * Sanity-checks surname length - 10/100 points
  * Sanity-checks country code - 15/100 points
  * Sanity-checks nationality - 10/100 points
  * Sanity-checks miscellaneous fields - 10/100 points
* EXIF check - can only decrease trust score 
 * Starts with 100 points
 * Remains on the same level if EXIF is blank
 * Remains on the same level if EXIF contains info about a digital camera
 * Checks if the EXIF fields contains info about image editing programs - -100/100 points

