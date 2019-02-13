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
 1. [operator name](#1-operator-name)
 2. [operator postcode](#2-operator-postcode)
 3. [operator first line](#3-operator-first-line)
 4. [operator street](#4-operator-street)
 5. [operator town](#5-operator-town)
 6. [contact representative name](#6-contact-representative-name)
 7. [contact representative role](#7-contact-representative-role)
 8. [contact representative number](#8-contact-representative-number)
 9. [contact representative email](#9-contact-representative-email)
 10. [operator primary number](#10-operator-primary-number)
 11. [operator secondary number](#11-operator-secondary-number)
 12. [operator email](#12-operator-email)
 13. [operator type](#13-operator-type)
 14. [operator company name](#14-operator-company-name)
 15. [operator company house number](#15-operator-company-house-number)
 16. [operator charity name](#16-operator-charity-name)
 17. [operator charity number](#17-operator-charity-number)
- [Establishment Premises](#establishment-premises)
- [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 1. [establishment postcode](#1-establishment-postcode)
 2. [establishment first line](#2-establishment-first-line)
 3. [establishment street](#3-establishment-street)
 4. [estabishment town](#4-estabishment-town)
 5. [establishment address type](#5-estabishment-address-type)
 - [Establishment Activities](#establishment-activities)
 - [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 1. [import export activities](#1-import-export-activities)
 2. [customer type](#2-customer-type)
 3. [business type](#3-buisness-type)
 4. [business type search term](#4-buisness-type-search-term)
 5. [business other details](#5-buisness-other-details)
 6. [opening day monday](#6-opening-day-monday)
 7. [opening day tuesday](#7-opening-day-tuesday)
 8. [opening day wednesday](8-opening-day-wednesday)
 9. [opening day thursday](#9-opening-day-thursday)
 10. [opening day friday](#10-opening-day-friday)
 11. [opening day saturday](#11-opening-day-saturday)
 12. [opening day sunday](#12-opening-day-sunday)
 13. [opening days irregular](#13-opening-days-irregular)
 - [Declaration and Metadata](#declaration-and-metadata)
 - [Field Definitions](#field-definitions) Complete definitions for each field in the standard, includes constraints and specific data type formatting requirements.  
 1. [declaration](#1-declaration)
 2. [fsa-rn](#2-fsa-rn)
 3. [reg submission date](#3-reg-submission-date)
 4. [trading start retroactive](#4-trading-start-retroactive)
 5. [trading start proactive](#5-trading-start-proactive)
 6. [pipeline config](#6-pipeline-config)
 7. [risk scores](#7-risk-scores)
 8. [inspection recommendation](#8-inspection-recommendation)
 9. [sent successfully](#9-sent-successfully)
 10. [send failed](#10-send-failed)
 11. [answer ids](#11-answer-ids)
 12. [local council](#12-local-council)


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

## Field Definitions

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

## Field Definitions


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
**Field Name:** `establishment Town`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 5. Establishment Address Type  
**Field Name:** `establishment address type`  
**Data Type:** boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown




## establishment activities Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.

Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data | Reason for collection | Sent to local council | Stored in tempoary Rof database | Reason for storage
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------|-----------------------|-----------------------|---------------------------------|-------------------
1|import export activities|unknown|String|predetermined values, "no import or export activities", "both import and export activities", "export activities" or "import activities"|String One of the allowed values ("Directly import","Directly export", "None", "Directly import and export")|NA|False|Informs risk and prioritisation|True|True|Informs risk calculations and improvements
2|customer type|unknown|string|predetermined value. "End consumer", "B2B" consumer or "End and B2B consumer"|String One of the allowed values ("Other businesses", "End consumer", "End consumer and other businesses")|NA|False|Informs risk and prioritisation|True|True|Informs risk calculations and improvements
3|business type|unknown|string|Predetermined values, see separate document for full business type list|String One of the allowed values from the business type list|NA|False|Informs risk and prioritisation|True|True|Informs risk calculations and improvements
4|business type search term|unknown|string|Predetermined values, see separate document for full business type list with search terms|NA|NA|Informs improvement of business type search feature|False|True|Informs improvement of business type search feature
5|business other details|unknown|String|All characters allowed. Personal information filtered|String less than 1550 characters|1550|False|Informs risk and prioritisation|True|True|Informs risk calculations and improvements
6|opening day monday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False|FBO contact and law enforcement|True|True|unknown
7|opening day tuesday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False|FBO contact and law enforcement|True|True|unknown
8|opening day wednesday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False|FBO contact and law enforcement|True|True|unknown
9|opening day thursday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False|FBO contact and law enforcement|True|True|unknown
10|opening day friday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False|FBO contact and law enforcement|True|True|unknown
11|opening day saturday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False|FBO contact and law enforcement|True|True|unknown
12|opening day sunday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False|FBO contact and law enforcement|True|True|unknown
13|opening day irregular|Unknown|String|All characters allowed|String less than 1550 characters|1550|False|FBO contact and law enforcement|True|True|unknown

## Field Definitions


### 1. Import export activities
**Field Name:** `import export activities`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 2. Customer Type
**Field Name:** `customer type`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 3. Business Type
**Field Name:** `Business Type`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 4. Business Type Search Term
**Field Name:** `buisness type search term`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 5. Business other details
**Field Name:** `Buisness other details`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 6. Opening Day Monday
**Field Name:** `opening day monday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 7. Opening Day Tuesday
**Field Name:** `opening day tuesday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 8. Opening Day Wednesday
**Field Name:** `opening day wednesday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 9. Opening Day Thursday
**Field Name:** `opening day thursday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 10. Opening Day Friday
**Field Name:** `opening day friday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 11. Opening Day Saturday
**Field Name:** `opening day saturday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 12. Opening Day Sunday
**Field Name:** `opening day sunday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 13. Opening Days Irregular
**Field Name:** `opening days irregular`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown



## Declaration and metadata Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.

Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data | Reason for collection | Sent to local council | Stored in tempoary Rof database | Reason for storage
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------|-----------------------|-----------------------|---------------------------------|-------------------
1|declaration|Unknown|String|preset values|custom validation to check if exists|NA|False|FBO contact and law enforcement|True|True|unknown
2|fsa-rn|string|only letters,numbers and dashes|NA|20|False|Enables linking of records to other FSA systems|True|True|Enables linking of records to other FSA systems
3|reg submission date|unknown|Date|ISO8061|NA|NA|False|Informs risk and prioritisation|True|True|Informs prioritisation calculation and enables understanding of FBO behaviour
4|trading start retroactive|unknown|date|ISO8061|Custom validation to check date is the same day or before the day calculated by the npm package moment|NA|False|unknown|True|True|Unknown
5|trading start proactive|unknown|date|ISO8061|Custom validation to check date is the same day or before the day calculated by the npm package moment|NA|False|unknown|True|True|Unknown
6|pipeline config|unknown|unknown|unknown|NA|unknown|False|NA|False|True|enables debugging of modular pipeline
7|risk scores|unknown|string|Predetermined values, "high", "medium" or "low"|NA|NA|False|NA|True|True|Informs risk calculations and improvements
8|inspection recommendation|unknown|string|predetermined values, "high", "medium" or "low"||NA|NA|False|NA|True|True|Informs prioritisation calculations and improvements
9|sent successfully|unknown|unknown|unknown|NA|unknown|False|NA|False|True|Enables debugging of transfer mechanisms
10|sent failed|unknown|unknown|unknown|NA|unknown|False|NA|False|True|Enables debugging of transfer mechanisms
11|answer ids|unknown|unknown|unknown|NA|unknown|False|NA|False|True|Enables debugging of transfer mechanisms
12|local council|unknown|String|values are predetermined from lookup service. Only letters and spaces max 50 carachters|NA|unknown|False|NA|True|True|Enables debugging of transfer mechanisms

## Field Definitions

### 1. Declaration
**Field Name:** `declaration`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 2. fsa-rn
**Field Name:** `fsa-rn`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 3. Reg Submission Date  
**Field Name:** `reg submission date`  
**Data Type:** date  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 4. Trading Start Retroactive
**Field Name:** `trading start retroactive`  
**Data Type:** date  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 5. Trading Start Proactive
**Field Name:** `trading start proactive`  
**Data Type:** date  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 6. Pipeline Config
**Field Name:** `pipeline config`  
**Data Type:** unknown  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 7. Risk Scores
**Field Name:** `Risk Scores`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 8. Inspection Recommendation
**Field Name:** `inspection recommendation`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 9. Sent Successfully
**Field Name:** `Sent Successfully`  
**Data Type:** unknown  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 10. Send Failed
**Field Name:** `send failed`  
**Data Type:** unknown
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 11. Answer IDs
**Field Name:** `answer ids`  
**Data Type:** unknown  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 12. Local Council
**Field Name:** `local council`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown
