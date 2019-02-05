# Register A Food Business Data Standard
### What Is This Document?
This document describes the data standard for Register a Food Business data collated by the Food Standards Agency from Food Business wishing to become approved with Local Authorities. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.
This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).
### Who Is This Document For?
This document is written for the FSA for the collation of data from Food Businesses.
### How This Document Is Structured
- [Establishment Data overview](#establishment-Data-Overview) Contains a brief overview of all the fields in the standard.  
- [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 1. [establishment trading name](#1-establishment-trading-name)
 2. [establishment primary number](#2-site-name)
 3. [establishment secondary number](#3-address)
 4. [establishment email](#4-cph-number)
 5. [establishment opening date](#5-certificate-end-date)
 6. [operator name](#6-red-tractor-dairy-number)
- [Establishment Operator Data Overview](#Establishment-Operator-Data-Overview)
- [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 7. [operator postcode](#7-last-rt-dairy-inspection-date)
 8. [operator first line]()
 9. [operator street]()
 10. [operator town]()
 11. [contact representative name]()
 12. [contact representative role]()
 13. [contact representative number]()
 14. [contact representative email]()
 15. [operator primary number]()
 16. [operator secondary number]()
 17. [operator email]()
 18. [operator type]()
 19. [operator company name]()
 20. [operator company house number]()
 21. [operator charity name]()
 22. [operator charity number]()
 23. [establishment postcode]()
 24. [establishment first line]()
 25. [establishment street]()
 26. [estabishment town]()
 27. [establishment address type]()
 28. [import export activities]()
 29. [customer type]()
 30. [business type]()
 31. [business type search term]()
 32. [business other details]()
 33. [opening day monday]()
 34. [opening day tuesday]()
 35. [opening day wednesday]()
 36. [opening day thursday]()
 37. [opening day friday]()
 38. [opening day saturday]()
 39. [opening day sunday]()
 40. [opening days irregular]()
 41. [declaration]()
 42. [fsa-rn]()
 43. [reg submission date]()
 44. [trading start retroactive]()
 45. [trading start proactive]()
 46. [pipeline config]()
 47. [risk scores]()
 48. [inspection recommendation]()
 49. [sent successfully]()
 50. [send failed]()
 51. [answer ids]()
 52. [local council]()
- [Supported File Types](#supported-file-types)
- [Other Requirements](#other-requirements)
- [File Naming Conventions](#file-naming-conventions)

## establishment Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data | Reason for collection | Sent to local council | Stored in tempoary Rof database | Reason for storage
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------|-----------------------|-----------------------|---------------------------------|-------------------
1|establishment trading name|unknown|String|Any character allowed|ASCII string|50|False|FBO contact and LC enforcement|True|True|Allows comparison of our data with returned FHRS data
2|establishment primary number|unknown|List of Strings|"+" and any numeric character allowed|Numeric string Between 5 and 20 charcaters (5 < x < 20) Allows "blank space" and "+"|15|True|FBO contact and LC enforcement|True|True|
3|establishment secondary number|unknown|List of Strings|"+" and any numeric character allowed|Numeric string Between 5 and 20 charcaters (5 < x < 20) Allows "blank space" and "+"|15|True|FBO contact and LC enforcement|True|True|
4|establishment email|unknown|String|must be email format|String npm validator isEmail |254|True|FBO contact and LC enforcement|True|True|
5|establishment opening date|unknown|ISO8061 Date|ISO date allowed characters|String npm validator isISO8601|11|False|FBO contact and LC enforcement|True|True|FBO registration analysis, risk correlation analysis

## Field Definitions

### 1. Establishment Trading Name
**Field Name:** `establishment trading name`  
**Data Type:** String
**Optional:** No  
**Source:** Food Standards Agency  
**Comments:** NA  

### 2. Establishment Primary Number
**Field Name:** `establishment primary number`  
**Data Type:** List of Strings ("+" and any numeric character allowed)
**Optional:** No  
**Source:** Food Standards Agency  
**Comments:** NA  

### 3. Establishment Secondary Number
**Field Name:** `establishment secondary number`  
**Data Type:** List of Strings ("+" and any numeric character allowed)   
**Optional:** No  
**Source:** Food Standards Agency  
**Comments:** NA   

### 4. Establishment Email
**Field Name:** `establishment email`  
**Data Type:** must be email format  
**Optional:** No  
**Source:** Food Standards Agency  
**Comments:** This is the County Parish Holding number, allocated to any establishment which holds livestock by the Rural Payments Agency. This should follow the format `nn/nnn/nnnn/nn`.  

### 5. Establishment Opening Date
**Field Name:** `establishment opening date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Red Tractor  
**Comments:** NA  

## Establishment Operator Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Optional | Controlled Vocabulary | Source
------|------------|-------------|-----------|----------|-----------------------|-------
1|fsa producer id|FSA producer unique identifier|Number|No|Yes|FSA

### 7. Last Red Tractor Dairy Inspection Date  
**Field Name:** `last rt dairy inspection date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Red Tractor  
**Comments:** The date of Red Tractor’s last inspection of the milk production establishment. This should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.

## establishment premisis Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Optional | Controlled Vocabulary | Source
------|------------|-------------|-----------|----------|-----------------------|-------
1|fsa producer id|FSA producer unique identifier|Number|No|Yes|FSA

### 7. Last Red Tractor Dairy Inspection Date  
**Field Name:** `last rt dairy inspection date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Red Tractor  
**Comments:** The date of Red Tractor’s last inspection of the milk production establishment. This should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.

## establishment activities Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Optional | Controlled Vocabulary | Source
------|------------|-------------|-----------|----------|-----------------------|-------
1|fsa producer id|FSA producer unique identifier|Number|No|Yes|FSA

### 7. Last Red Tractor Dairy Inspection Date  
**Field Name:** `last rt dairy inspection date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Red Tractor  
**Comments:** The date of Red Tractor’s last inspection of the milk production establishment. This should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.

## Declaration and metadata Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Optional | Controlled Vocabulary | Source
------|------------|-------------|-----------|----------|-----------------------|-------
1|fsa producer id|FSA producer unique identifier|Number|No|Yes|FSA

### 7. Last Red Tractor Dairy Inspection Date  
**Field Name:** `last rt dairy inspection date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Red Tractor  
**Comments:** The date of Red Tractor’s last inspection of the milk production establishment. This should follow the YYYY-MM-DD format as laid out in the International Standard ISO 8601.

















## Supported File Types

Currently we are supporting the standard for comma separated values (CSV), Json and XML files.

The [current standard for CSV](https://tools.ietf.org/html/rfc4180) gives a detailed explanation of the common format for CSV files. It's concise and clear and we recommend reading it.

## Other Requirements

### Text Fields

The majority of the fields in the standard are text, which needs to be treated carefully when stored in a CSV file. All text fields must be enclosed within double quotes `"this is the text"`. You should try to avoid using double quotes within a text field as this can cause the field to be misread, but the RFC4180 standard allows it if handled appropriately.

>If double-quotes are used to enclose fields, then a double-quote appearing inside a field must be escaped by preceding it with another double quote. For example: `"aaa","b""bb","ccc"`

### Encoding

Where possible please use `UTF-8` encoding.

## File Naming Conventions

In order to make it easy for us to manage the files longer term, it will be important to name files so that we can tell the time period that each file covers. The format will be RT and the date and time of submission in `YYYYMMDD-HHMMSS` format.

For example, the file submitted the 31st of January 2017 15:20:33 would be named `RT20170131-152033.csv`.
