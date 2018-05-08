Storage rules: issue package files
==================================

Issue package file is an archive file which contains all contents of articles belonging to single issue. Article contents include article XML, PDF of aticle, figures and graphics optional, as well as supplementary materials.

This document convers issue package storage rules and is applicable to Aging, Oncotarget, Oncoscience and Genes and Cancer journals.


For simplicity we structured these rules around 3 possible scenarios:

- Initial package upload
- Corrected package upload (after validation)
- Revision package upload (incremental upload when article is already on PMC)



Initial package upload
======================

Initial package upload happens when issue package file is being uploaded to SFTP server for the first time. For all subsequet uploads please check "Corrected package upload" or "Revision package upload".


Naming of issue pakage file
---------------------------

Issue package files should be named in accordance with PMC guidelines.

Use the following naming scheme: jour-vol-issue.zip

- **jour** is an alphanumeric identifier such as a journal abbreviation.

  +-----------------------------+--------------+ 
  | Journal                     |  jour        | 
  +=============================+==============+ 
  | Aging                       | aging        | 
  +-----------------------------+--------------+ 
  | Oncotarget                  | oncotarget   | 
  +-----------------------------+--------------+ 
  | Oncoscience                 | oncoscience  | 
  +-----------------------------+--------------+ 
  | Genes and Cancer            | ganc         | 
  +-----------------------------+--------------+ 


- **vol** is journal volume
- **issue** identifies a specific journal issue

| For example:
|
| aging-10-01.zip
| oncotarget-09-12.zip
| oncoscience-05-01-02.zip

.. IMPORTANT::
	
  Please use hyphens (-) to separate parts file name. Other charcter (such as underscores, dots, etc) are not allowed.



Package files target location
-----------------------------
Issue package file should be uploaded to corresponding SFTP folder.


Use the following location to store issue packages:

/mnt/archive_mount/pmcarchive/in_house/[Journal]/[v#]/[aging-vol-issue]/[storage-date]

- **Journal** - possible values: "Aging", "Oncotarget", "Oncoscience", "Genes&Cancer".

- **v#** stands for letter "v" and volume number (e.g. v8, v9, v2 etc)

- **aging-vol-issue** is "aging" word followed by volume and issue numbers (e.g. aging-10-1, aging-5-6, aging-9-2 etc)

- **storage-date** is the date when file was uploaded to the server. 

Use the following naming convention for storge date: YYYYMMDD

- YYYY is full year (e.g. 2018, 2019 etc)

- MM is two-digit month (e.g. 01, 05, 10, 12 etc)

- DD is two-digit day (e.g. 01, 20, 25, 31 etc)


Example:

We have a file named aging-10-01.zip for Aging Journal, volume 10 and issue 1. We need to place it on the server on the 30'th of January 2018.

In this case, full path to the file will be:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130/aging-10-01.zip




Corrected package upload (after validation)
===========================================

After initial upload (see above), issue package is validated against set of criteria to make sure that quality of package meets PMC standards. If there are issues, vendors re-package corrected files and upload full issue package to SFTP again. 


Naming of issue pakage file
---------------------------

.. Note::
    
    Naming of issue package here is the same as for "Initial package upload" scenario.


Issue package files should be named in accordance with PMC guidelines.

Use the following naming scheme: jour-vol-issue.zip

- *jour* is an alphanumeric identifier such as a journal abbreviation.

  +-----------------------------+--------------+ 
  | *Journal*                   | *jour*       | 
  +=============================+==============+ 
  | Aging                       | aging        | 
  +-----------------------------+--------------+ 
  | Oncotarget                  | oncotarget   | 
  +-----------------------------+--------------+ 
  | Oncoscience                 | oncoscience  | 
  +-----------------------------+--------------+ 
  | Genes and Cancer            | ganc         | 
  +-----------------------------+--------------+ 


- *vol* is journal volume
- *issue* identifies a specific journal issue

| For example:
|
| aging-10-01.zip
| oncotarget-09-12.zip
| oncoscience-05-01-02.zip

.. IMPORTANT::
  
  Please use hyphens (-) to separate parts file name. Other charcter (such as underscores, dots, etc) are not allowed.


Package files target location
-----------------------------

.. IMPORTANT::
    
    Package files target location here *DIFFERS* from "Initial package upload" scenario.


Issue package file should be uploaded to corresponding SFTP folder.


Use the following location to store issue packages:

/mnt/archive_mount/pmcarchive/in_house/[Journal]/[v#]/[aging-vol-issue]/[storage-date]
OR
/mnt/archive_mount/pmcarchive/in_house/[Journal]/[v#]/[aging-vol-issue]/[storage-date-iteration]

- *Journal* - possible values: "Aging", "Oncotarget", "Oncoscience", "Genes&Cancer".
- *v#* stands for letter "v" and volume number (e.g. v8, v9, v2 etc)
- *aging-vol-issue* is "aging" word followed by volume and issue numbers (e.g. aging-10-1, aging-5-6, aging-9-2 etc)
- *storage-date* is the date when file was uploaded to the server
OR
- storage-date-iteration is used when corrections are uploaded same date as initial package. In this case add "iteration" number to the date 

Use the following naming convention for storge date: YYYYMMDD or YYYYMMDD-[iteration number]
- YYYY is full year (e.g. 2018, 2019 etc)
- MM is two-digit month (e.g. 01, 05, 10, 12 etc)
- DD is two-digit day (e.g. 01, 20, 25, 31 etc)
- iteration number is one digit number (i.e. 1, 2, 3 etc)



Example 1 (different upload dates):

We have corrected package file named aging-10-01.zip for Aging Journal volume 10 and issue 1. We need to place it on the server on the 3'd of February, 2018. At the same time initial upload has been done on the 30'th of January, 2018.

In this case, full path to the file will be:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180203/aging-10-01.zip

As a result we will have 2 files on the server - initial and corrected:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130/aging-10-01.zip
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180203/aging-10-01.zip



Example 2 (same upload date):

We have corrected package file named aging-10-01.zip for Aging Journal volume 10 and issue 1. We need to place it ont the server on the same date when initial upload has been done - 30'th of January, 2018.

In such case we create a folder with the same date *AND* iteration number - 20180130-1 - and place the file there:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130-1/aging-10-01.zip


As a result we will have 2 files on the server - initial and corrected:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130/aging-10-01.zip
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130-1/aging-10-01.zip



Revision package upload (incremental upload when article is already on PMC)
===========================================================================

If there is a need to make corrections to article file(s) after issue package has passed evaluation stage of PMC, then those corrections should be uploaded to PMC as a revision package.


This should be done in accordance with PMC requirenments: Please resubmit only the files that have been modified, along with their corresponding XML files. Do NOT change the file names of the resupplied files, only change the package name to indicate a revision (see below)


Naming of issue pakage file
---------------------------

.. IMPORTANT::
    
    Naming of issue package here *DIFFERS* from "Initial package upload" scenario.


Issue package files should be named in accordance with PMC guidelines.

Use the following naming scheme: jour-vol-issue.r#.zip

- *jour* is an alphanumeric identifier such as a journal abbreviation.

  +-----------------------------+--------------+ 
  | *Journal*                   | *jour*       | 
  +=============================+==============+ 
  | Aging                       | aging        | 
  +-----------------------------+--------------+ 
  | Oncotarget                  | oncotarget   | 
  +-----------------------------+--------------+ 
  | Oncoscience                 | oncoscience  | 
  +-----------------------------+--------------+ 
  | Genes and Cancer            | ganc         | 
  +-----------------------------+--------------+ 


- *vol* is journal volume
- *issue* identifies a specific journal issue
- *r#* is a revision number (e.g. r1, r2, r3)


For example:

-You send the original files for "Aging" volume 10, issue 1 in a zip file named:  *aging-15-01.zip*

- Three days later, you send a revised XML file for one article, in a zip file named: *aging-15-01.r1.zip*

- Later that same day, you send replacement files for the same issue, in a zip file named: *aging-15-01.r2.zip*


.. IMPORTANT::
  
  Please use hyphens (-) to separate parts file name. Other charcter (such as underscores, dots, etc) are not allowed.


Package files target location
-----------------------------

.. IMPORTANT::
    
    Package files target location here *DIFFERS* from "Initial package upload" scenario.


Issue package file should be uploaded to corresponding SFTP folder.


Use the following location to store issue packages:

/mnt/archive_mount/pmcarchive/in_house/[Journal]/[v#]/[aging-vol-issue]/[storage-date]
OR
/mnt/archive_mount/pmcarchive/in_house/[Journal]/[v#]/[aging-vol-issue]/[storage-date-iteration]

- *Journal* - possible values: "Aging", "Oncotarget", "Oncoscience", "Genes&Cancer".
- *v#* stands for letter "v" and volume number (e.g. v8, v9, v2 etc)
- *aging-vol-issue* is "aging" word followed by volume and issue numbers (e.g. aging-10-1, aging-5-6, aging-9-2 etc)
- *storage-date* is the date when file was uploaded to the server
OR
- storage-date-iteration is used when corrections are uploaded same date as initial package. In this case add "iteration" number to the date 

Use the following naming convention for storge date: YYYYMMDD or YYYYMMDD-[iteration number]
- YYYY is full year (e.g. 2018, 2019 etc)
- MM is two-digit month (e.g. 01, 05, 10, 12 etc)
- DD is two-digit day (e.g. 01, 20, 25, 31 etc)
- iteration number is one digit number (i.e. 1, 2, 3 etc)



Example 1 (different upload dates):

We have a revision file named aging-10-01.r1.zip for Aging Journal volume 10 and issue 1. We need to place it on the server on the 3'd of February, 2018. At the same time initial upload has been done on the 30'th of January, 2018.

In this case, full path to the file will be:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180203/aging-10-01.zip

As a result we will have 2 files on the server - initial and corrected:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130/aging-10-01.zip
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180203/aging-10-01.r1.zip



Example 2 (same upload date):

We have a revision file named aging-10-01.r1.zip for Aging Journal volume 10 and issue 1. We need to place it on the server on the same date when initial upload has been done - 30'th of January, 2018.

In such case we create a folder with the same date *AND* iteration number - 20180130-1 - and place the file there:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130-1/aging-10-01.zip


As a result we will have 2 files on the server - initial and corrected:
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130/aging-10-01.zip
/mnt/archive_mount/pmcarchive/in_house/Aging/v10/aging-10-1/20180130-1/aging-10-01.r1.zip

