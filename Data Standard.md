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
 2. [establishment primary number](#2-establishment-primary-number)
 3. [establishment secondary number](#3-establishment-secondary-number)
 4. [establishment email](#4-establishment-email)
 5. [establishment opening date](#5-establishment-opening-date)
 - [Establishment Operator Data Overview](#Establishment-Operator-Data-Overview)
 - [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 1. [operator name](#6-red-tractor-dairy-number)
 2. [operator postcode](#7-last-rt-dairy-inspection-date)
 3. [operator first line]()
 4. [operator street]()
 5. [operator town]()
 6. [contact representative name]()
 7. [contact representative role]()
 8. [contact representative number]()
 9. [contact representative email]()
 10. [operator primary number]()
 11. [operator secondary number]()
 12. [operator email]()
 13. [operator type]()
 14. [operator company name]()
 15. [operator company house number]()
 16. [operator charity name]()
 17. [operator charity number]()
- [Establishment Premises](#establishment-premises)
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

## Establishment Data Overview
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
**Source:** unknown
**Comments:** unknown

### 2. Establishment Primary Number
**Field Name:** `establishment primary number`  
**Data Type:** List of Strings ("+" and any numeric character allowed)
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 3. Establishment Secondary Number
**Field Name:** `establishment secondary number`  
**Data Type:** List of Strings ("+" and any numeric character allowed)   
**Optional:** No  
**Source:** unknown
**Comments:** unknown  

### 4. Establishment Email
**Field Name:** `establishment email`  
**Data Type:** must be email format  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 5. Establishment Opening Date
**Field Name:** `establishment opening date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

## Establishment Operator Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data | Reason for collection | Sent to local council | Stored in tempoary Rof database | Reason for storage
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------|-----------------------|-----------------------|---------------------------------|-------------------
1|operator name|unknown|String|Any character allowed|ASCII string|70|True|FBO contact and LC enforcement|True|False|NA
2|operator postcode|string|only numbers and letters allowed, min 3 max 8 characters|String npm validator isPostalCode (GB)|8|True|FBO contact and LC enforcement|True|False|NA
3|operator first line |string|Any characters allowed|ASCII string|256|true|FBO contact and LC enforcement|True|False||
4|operator street||string|Any characters allowed|ASCII string|256|true|FBO contact and LC enforcement|True|False||
5|operator town|string|Any characters allowed|ASCII string|256|true|FBO contact and LC enforcement|True|False||
6|contact representative name|string|Any characters allowed|ASCII string|70|true|FBO contact and LC enforcement|True|False||
7|contact representative role|string|Any characters allowed|ASCII string|256|true|FBO contact and LC enforcement|True|False||
8|contact representative number|string|Any characters allowed|ASCII string|15|true|FBO contact and LC enforcement|True|False||
9|contact representative email|string|standard email format|String npm validator isEmail|254|True|FBO contact and LC enforcement|True|False||
10|operator primary number|string|"+" and any numeric character allowed|Numeric string Between 5 and 20 charcaters (5 < x < 20) Allows "blank space" and "+"|15|True|FBO contact and LC enforcement|True|False||
11|operator secondary number|string|"+" and any numeric character allowed|Numeric string Between 5 and 20 charcaters (5 < x < 20) Allows "blank space" and "+"|15|True|FBO contact and LC enforcement|True|False||
12|operator email|string|standard email format|String npm validator isEmail|254|True|FBO contact and LC enforcement|True|False|NA
13|operator type|string|predetermined values. "I represent a person which operates this business", "I represent a charity which operates this business", "I represent a company which operates this business", "sole trader" or "partnership"|Radio button validation (i.e. whether one has been selected or not)|NA|False|Informs risk and prioritisation|True|True|Informs risk and prioritisation calculations, allows analytics of user group spread
14|operator_company name|string|Any character allowed|String less than 50 characters|50|True|Local Council use this to validate registration details|True|False|NA
15|operator company house number|string|Only letters and numbers allowed|String npm validator isAlphanumeric (GB) 8 Characters in length First two characters numeric|8|True|Local Council use this to validate registration details|True|True|NA
16|operator charity name|string|Any character allowed|String Less than 50 characters|50|True|Local Council use this to validate registration details|True|False|NA
17|operator charity number|string|Only letters, numbers and dashes allowed|String Allows "-" Between 6 to 8 characters in length (6 < x < 8) npm validator isAlphanumeric (GB)|8|True|Local Council use this to validate registration details|True|True|NA



### 1. Operator Name  
**Field Name:** `operator name`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 2. Operator Postcode  
**Field Name:** `operator postcode`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 3. Operator Fist Line  
**Field Name:** `operator first line`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 4. Operator Street  
**Field Name:** `operator street`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 5. Operator Town  
**Field Name:** `operator Town`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 6. Contact Representative Name  
**Field Name:** `Contact Representative Name`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 7. Contact Representative Role  
**Field Name:** `Contact Representative Role`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 8. Contact Representative Number  
**Field Name:** `Contact Representative Number`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 9. Contact Representative Email  
**Field Name:** `Contact Representative Email`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 10. Operator Primary Number  
**Field Name:** `operator primary number`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 11. Operator Secondary Number  
**Field Name:** `operator secondary number`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 12. Operator Email  
**Field Name:** `operator email`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 13. Operator Type  
**Field Name:** `operator type`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 14. Operator Secondary Number  
**Field Name:** operator secondary number  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 15. Operator Secondary Number  
**Field Name:** operator secondary number  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 16. Operator Secondary Number  
**Field Name:** operator secondary number  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 17. Operator Secondary Number  
**Field Name:** operator secondary number  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown



## establishment premises Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data | Reason for collection | Sent to local council | Stored in tempoary Rof database | Reason for storage
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------|-----------------------|-----------------------|---------------------------------|-------------------
1|establishment postcode|unknown|String|Only numbers, letters and spaces allowed|String npm validator isPostalCode (GB)|8|False|FBO contact and LC enforcement|True|True|Allows comparison of our data with returned FHRS data
2|establishment first line |string|Any characters allowed|ASCII string|256|False|FBO contact and LC enforcement|True|True||
4|estabishment street||string|Any characters allowed|ASCII string|256|False|FBO contact and LC enforcement|True|True||
5|estabishment town|string|Any characters allowed|ASCII string|256|False|FBO contact and LC enforcement|True|True||
6|establishment address type|boolean|Predetermined values|Radio button validation (i.e. whether one has been selected or not)|NA|False|FBO contact and LC enforcement|True|True|Informs risk calculations and improvements


### 1. Establishment Postcode  
**Field Name:** `establishment postcode`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 2. Establishment Fist Line  
**Field Name:** `establishment first line`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 3. Establishment Street  
**Field Name:** `establishment street`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 4. Establishment Town  
**Field Name:** `estabishment Town`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 5. Establishment Address Type  
**Field Name:** `estabishment address type`  
**Data Type:** boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown




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
