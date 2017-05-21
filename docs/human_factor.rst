.. _human_factor:

Human factor verification
=========================

PassportEye is capable of detecting simplest ways to work around the document verification
process, while remaining user-friendly and providing seamless integration with the platform
using it. As the industry experience shows, it's easy to check if the provided document conforms 
to specifications, but it's harder to check if it conforms to reality.

PassportEye sanity-checks provided documents to notify about most common mistakes that are 
typically made by users, as well as check for workarounds which have been used to bypass 
most common document verification schemes. The checks included are:


* Verification that the **image provided has an actual identification document**, using a database \
  of identification documents. As PassportEye is not supposed the, the validity score influence \
  of this check is inversely proportional to the current size of PassportEye database.
* Verification against **social media profiles**, calculating profile validity score and \ 
  accounting for it while calculating the overall trust score. Currently, PassportEye has \
  Facebook, Google+, MySpace and Twitter integration.
* Verification of the **document expiration date**, comparing it to current date and asking the user 
  to submit a valid document in case the provided document has expired.
* **Sanity-checks** for document **issue/expiration date**, notifying users about expired documents \
  and not accepting them as valid. When the issue and expiration dates aren't realistic, \
  it notifies the platform about possible document falsification.
* Checks for **file size, magic markers and resolution** of provided file to prevent possible DoS \
  attacks on PassportEye service. The scenarios covered by this check include submitting \
  artificially-crafted images that consume operating memory of the system, submitting files \
  that are designed to be interpreted as malicious code, as well as submitting files of unnecessarily high resolution. 
* Checks for **documents that already went through validation** and yielded unfavorable results, \
  notifying the platform about such occasions. The scenarios covered by this check include \
  customers that are trying to game the platform by submitting same document on different platforms, \
  hoping that either the platforms in question are using inferior verification systems (or \
  none at all), or that the verification system provides non-deterministic results. 
