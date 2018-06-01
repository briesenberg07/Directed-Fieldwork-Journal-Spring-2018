# Preparing Files for HathiTrust Ingest
A number of steps remained between digital capture using post-processing of page image files and upload to the HathiTrust.
## Optical Character Recognition
Finished image files were loaded into Abbyy FineReader optical character recognition (OCR) software to generate plain text files for each individual page.  
The HathiTrust accepts more complex files which include both textual content as well as information about the position of words on the page. However, the OCR software available at the time of the project was not capable of generating such a file in any of the accepted formats, so this potential process improvement was put off until later. 
## YAML file generation
The HathiTrust requires that page image files be packaged together with a simple file containing information about the digital capture of items as well as page tags and other information that describe the structure of the book and allow it to be presented properly online. This information includes the following items (from **[HathiTrust Cloud Validation and Packaging Service](https://docs.google.com/document/d/1OQ0SKAiOH8Xi0HVVxg4TryBrPUPtdv4qA70d8ghRltU/edit)**):
- Date the item was scanned (REQUIRED)
- Organization that scanned the item (REQUIRED)
- Information about the scanner that was used (OPTIONAL)
- Information about image resolution (REQUIRED if missing from images)
- Information about when and how images were compressed or converted (OPTIONAL)
- The page number corresponding to each file (OPTIONAL)
- Page tags (e.g. COVER, TABLE_OF_CONTENTS) (OPTIONAL)  

While these files had previously been generated manually, my DFW supervisor directed me to **[a GitHub repository containing a Python script to automate the process](https://github.com/ruthtillman/yaml-generator-for-hathitrust)**. This repository, created for use at Notre Dame, provided the script as well as extensive documentation explaining how to enter data into a spreadsheet which could then be processed to output a YAML file containing all necessary values.  
I was able to successfully utilize a slightly-modified version of this script to generate YAML files for all 14 of my digitized items. 
This version, which now includes default values reflecting workflows in the Preservation Services unit, is available in a new **[GitHub repository](https://github.com/briesenberg07/HathiTrustYAMLgenerator)**. Ownership of the repository has been transferred to my DFW supervisor in the Preservation Services unit, and hopefully this will allow for ongoing improvements to the script itself. I also compiled documentation from sources including the original repository as well as the HathiTrust, restructuring and enriching it with the intent to make the process of entering item information in a provided data-entry template (spreadsheet) and processing this data to output YAML files as easy as possible. Transferring ownership of the repository to the Preservation Services unit should also allow for ongoing improvements to the associated documentation.
## Generating Checksums
The last step in the process was generating md5 checksums for the page images, OCR-generated text files, and YAML files. These checksums will be used by the HathiTrust to ensure the integrity of submitted digital objects over time. 


