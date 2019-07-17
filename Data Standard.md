# Register A Food Business Data Standard
### What Is This Document?
This document describes the data standard for Register a Food Business data collated by the Food Standards Agency from Food Business wishing to become approved with Local Authorities. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.
This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).
### Who Is This Document For?
This document is written for the FSA for the collation of data from Food Businesses.
### How This Document Is Structured
- [Establishment_Data_overview](#establishment-Data-Overview)
 1. [establishment_trading_name](#1-establishment-trading-name)
 2. [establishment_primary_number](#2-establishment-primary-number)
 3. [establishment_secondary_number](#3-establishment-secondary-number)
 4. [establishment_email](#4-establishment-email)
 5. [establishment_opening_date](#5-establishment-opening-date)
 - [Establishment Operator Data Overview](#Establishment-Operator-Data-Overview)
 1. [operator_name](#1-operator-name)
 2. [operator_postcode](#2-operator-postcode)
 3. [operator_first_line](#3-operator-first-line)
 4. [operator_street](#4-operator-street)
 5. [operator_town](#5-operator-town)
 6. [contact_representative_name](#6-contact-representative-name)
 7. [contact_representative_role](#7-contact-representative-role)
 8. [contact_representative_number](#8-contact-representative-number)
 9. [contact_representative_email](#9-contact-representative-email)
 10. [operator_primary_number](#10-operator-primary-number)
 11. [operator_secondary_number](#11-operator-secondary-number)
 12. [operator_email](#12-operator-email)
 13. [operator_type](#13-operator-type)
 14. [operator_company_name](#14-operator-company-name)
 15. [operator_company_house_number](#15-operator-company-house-number)
 16. [operator_charity_name](#16-operator-charity-name)
 17. [operator_charity_number](#17-operator-charity-number)
- [Establishment Premises](#establishment-premises)
 1. [establishment_postcode](#1-establishment-postcode)
 2. [establishment_first_line](#2-establishment-first-line)
 3. [establishment_street](#3-establishment-street)
 4. [estabishment_town](#4-estabishment-town)
 5. [establishment_address_type](#5-estabishment-address-type)
 - [Establishment_Activities](#establishment-activities)
 1. [import_export_activities](#1-import-export-activities)
 2. [customer_type](#2-customer-type)
 3. [business_type](#3-buisness-type)
 4. [business_type_search_term](#4-buisness-type-search-term)
 5. [business_other_details](#5-buisness-other-details)
 6. [opening_day_monday](#6-opening-day-monday)
 7. [opening_day_tuesday](#7-opening-day-tuesday)
 8. [opening_day_wednesday](8-opening-day-wednesday)
 9. [opening_day_thursday](#9-opening-day-thursday)
 10. [opening_day_friday](#10-opening-day-friday)
 11. [opening_day_saturday](#11-opening-day-saturday)
 12. [opening_day_sunday](#12-opening-day-sunday)
 13. [opening_days_irregular](#13-opening-days-irregular)
 - [Declaration and Metadata](#declaration-and-metadata)
 1. [declaration](#1-declaration)
 2. [fsa-rn](#2-fsa-rn)
 3. [reg_submission_date](#3-reg-submission-date)
 4. [trading_start_retroactive](#4-trading-start-retroactive)
 5. [trading_start_proactive](#5-trading-start-proactive)
 6. [pipeline_config](#6-pipeline-config)
 7. [risk_scores](#7-risk-scores)
 8. [inspection_recommendation](#8-inspection-recommendation)
 9. [sent_successfully](#9-sent-successfully)
 10. [send_failed](#10-send-failed)
 11. [answer_ids](#11-answer-ids)
 12. [local_council](#12-local-council)


## Establishment Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------
1|establishment_trading_name|The proposed trading name of the new food business|String|Any character allowed|ASCII string|50|False
2|establishment_primary_number|unknown|List of Strings|"+" and any numeric character allowed|Numeric string Between 5 and 20 characters (5 < x < 20) Allows "blank space" and "+"|15|True
3|establishment_secondary number|unknown|List of Strings|"+" and any numeric character allowed|Numeric string Between 5 and 20 charcaters (5 < x < 20) Allows "blank space" and "+"|15|True
4|establishment_email|Email address for the proposed food business|String|must be email format|String npm validator isEmail |254|True
5|establishment_opening_date|Estimated opening date for the proposed food business|ISO8061 Date|ISO date allowed characters|String npm validator isISO8601|11|False

## Field Definitions

### 1. Establishment Trading Name
**Field Name:** `establishment_trading_name`  
**Data Type:** String
**Optional:** No  
**Source:** Submitted by service user
**Comments:** The proposed trading name of the new food business

### 2. Establishment Primary Number
**Field Name:** `establishment_primary_number`  
**Data Type:** List of Strings ("+" and any numeric character allowed)
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 3. Establishment Secondary Number
**Field Name:** `establishment_secondary_number`  
**Data Type:** List of Strings ("+" and any numeric character allowed)   
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown  

### 4. Establishment Email
**Field Name:** `establishment_email`  
**Data Type:** must be email format  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** Email address for the proposed food business

### 5. Establishment Opening Date
**Field Name:** `establishment_opening_date`  
**Data Type:** Date (format: `YYYY-MM-DD`)  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** Estimated opening date for the proposed food business

## Establishment Operator Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------
1|operator_name|Full name of the proposed food business operator|String|Any character allowed|ASCII string|70|True
2|operator_postcode|string|only numbers and letters allowed, min 3 max 8 characters|String npm validator isPostalCode (GB)|8|True
3|operator_first_line |string|Any characters allowed|ASCII string|256|true
4|operator_street||string|Any characters allowed|ASCII string|256|true
5|operator_town|string|Any characters allowed|ASCII string|256|true
6|contact_representative_name|string|Any characters allowed|ASCII string|70|true
7|contact_representative_role|string|Any characters allowed|ASCII string|256|true
8|contact_representative_number|string|Any characters allowed|ASCII string|15|true
9|contact_representative_email|string|standard email format|String npm validator isEmail|254|True
10|operator_primary_number|string|"+" and any numeric character allowed|Numeric string Between 5 and 20 charcaters (5 < x < 20) Allows "blank space" and "+"|15|True
11|operator_secondary_number|string|"+" and any numeric character allowed|Numeric string Between 5 and 20 charcaters (5 < x < 20) Allows "blank space" and "+"|15|True
12|operator_email|string|standard email format|String npm validator isEmail|254|True
13|operator_type|string|predetermined values. "I represent a person which operates this business", "I represent a charity which operates this business", "I represent a company which operates this business", "sole trader" or "partnership"|Radio button validation (i.e. whether one has been selected or not)|NA|False
14|operator_company name|string|Any character allowed|String less than 50 characters|50|True
15|operator_company_house number|string|Only letters and numbers allowed|String npm validator isAlphanumeric (GB) 8 Characters in length First two characters numeric|8|True
16|operator_charity_name|string|Any character allowed|String Less than 50 characters|50|True
17|operator_charity_number|string|Only letters, numbers and dashes allowed|String Allows "-" Between 6 to 8 characters in length (6 < x < 8) npm validator isAlphanumeric (GB)|8|True

## Field Definitions

### 1. Operator Name  
**Field Name:** `operator_name`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** Full name of the proposed food business operator

### 2. Operator Postcode  
**Field Name:** `operator_postcode`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 3. Operator First Line  
**Field Name:** `operator_first_line`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 4. Operator Street  
**Field Name:** `operator_street`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 5. Operator Town  
**Field Name:** `operator_town`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 6. Contact Representative Name  
**Field Name:** `contact_representative_name`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 7. Contact Representative Role  
**Field Name:** `contact_representative_role`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 8. Contact Representative Number  
**Field Name:** `contact_representative_number`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 9. Contact Representative Email  
**Field Name:** `contact_representative_email`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 10. Operator Primary Number  
**Field Name:** `operator_primary_number`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 11. Operator Secondary Number  
**Field Name:** `operator_secondary_number`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 12. Operator Email  
**Field Name:** `operator_email`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 13. Operator Type  
**Field Name:** `operator_type`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 14. Operator Secondary Number  
**Field Name:** `operator_secondary_number`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 15. Operator Secondary Number  
**Field Name:** `operator_secondary_number`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 16. Operator Secondary Number  
**Field Name:** `operator_secondary_number`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 17. Operator Secondary Number  
**Field Name:** `operator_secondary_number`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string



## establishment premises Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.


Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------
1|establishment_postcode|unknown|String|Only numbers, letters and spaces allowed|String npm validator isPostalCode (GB)|8|False
2|establishment_first_line |string|Any characters allowed|ASCII string|256|False
3|estabishment_street||string|Any characters allowed|ASCII string|256|False
4|estabishment_town|string|Any characters allowed|ASCII string|256|False
5|establishment_address type|boolean|Predetermined values|Radio button validation (i.e. whether one has been selected or not)|NA|False

## Field Definitions


### 1. Establishment Postcode  
**Field Name:** `establishment_postcode`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 2. Establishment First Line  
**Field Name:** `establishment_first_line`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 3. Establishment Street  
**Field Name:** `establishment_street`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 4. Establishment Town  
**Field Name:** `establishment_Town`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** string

### 5. Establishment Address Type  
**Field Name:** `establishment_address_type`  
**Data Type:** boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** boolean




## establishment activities Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.

Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------
1|import_export_activities|unknown|String|predetermined values, "no import or export activities", "both import and export activities", "export activities" or "import activities"|String One of the allowed values ("Directly import","Directly export", "None", "Directly import and export")|NA|False
2|customer_type|unknown|string|predetermined value. "End consumer", "B2B" consumer or "End and B2B consumer"|String One of the allowed values ("Other businesses", "End consumer", "End consumer and other businesses")|NA|False
3|business_type|unknown|string|Predetermined values, see separate document for full business type list|String One of the allowed values from the business type list|NA|False
4|business_type_search_term|unknown|string|Predetermined values, see separate document for full business type list with search terms|NA|NA
5|business_other_details|unknown|String|All characters allowed. Personal information filtered|String less than 1550 characters|1550|False
6|opening_day_monday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False
7|opening_day_tuesday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False
8|opening_day_wednesday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False
9|opening_day_thursday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False
10|opening_day_friday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False
11|opening_day_saturday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False
12|opening_day_sunday|Unknown|Boolean|Only true or false allowed.|True or False|NA|False
13|opening_day_irregular|Unknown|String|All characters allowed|String less than 1550 characters|1550|False

## Field Definitions


### 1. Import export activities
**Field Name:** `import_export_activities`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 2. Customer Type
**Field Name:** `customer_type`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 3. Business Type
**Field Name:** `business_type`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 4. Business Type Search Term
**Field Name:** `buisness_type_search_term`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 5. Business other details
**Field Name:** `buisness_other_details`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 6. Opening Day Monday
**Field Name:** `opening_day_monday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 7. Opening Day Tuesday
**Field Name:** `opening_day_tuesday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 8. Opening Day Wednesday
**Field Name:** `opening_day_wednesday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 9. Opening Day Thursday
**Field Name:** `opening_day_thursday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 10. Opening Day Friday
**Field Name:** `opening_day_friday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 11. Opening Day Saturday
**Field Name:** `opening_day_saturday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 12. Opening Day Sunday
**Field Name:** `opening_day_sunday`  
**Data Type:** Boolean  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 13. Opening Days Irregular
**Field Name:** `opening_days_irregular`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown



## Declaration and metadata Data Overview
The following table lists the fields (name and description), their data types, whether they are optional, and whether they use a controlled vocabulary.

Index | Field Name | Description | Data Type | Validation rule | Validation implemented | Max character length | Personal Data
------|------------|-------------|-----------|-----------------|------------------------|----------------------|---------------
1|declaration|Unknown|String|preset values|custom validation to check if exists|NA|False
2|fsa-rn|string|only letters,numbers and dashes|NA|NA|20|False
3|reg_submission_date|unknown|Date|ISO8061|NA|NA|False
4|trading_start_retroactive|unknown|date|ISO8061|Custom validation to check date is the same day or before the day calculated by the npm package moment|NA|False
5|trading_start_proactive|unknown|date|ISO8061|Custom validation to check date is the same day or before the day calculated by the npm package moment|NA|False
6|pipeline_config|unknown|unknown|unknown|NA|unknown|False
7|risk_scores|unknown|string|Predetermined values, "high", "medium" or "low"|NA|NA|False
8|inspection_recommendation|unknown|string|predetermined values, "high", "medium" or "low"||NA|NA|False
9|sent_successfully|unknown|unknown|unknown|NA|unknown|False
10|sent_failed|unknown|unknown|unknown|NA|unknown|False
11|answer_ids|unknown|unknown|unknown|NA|unknown|False
12|local_council|unknown|String|values are predetermined from lookup service. Only letters and spaces max 50 characters|NA|unknown|False

## Field Definitions

### 1. Declaration
**Field Name:** `declaration`  
**Data Type:** string  
**Optional:** No  
**Source:** Submitted by service user
**Comments:** unknown

### 2. fsa-rn
**Field Name:** `fsa-rn`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** string

### 3. Reg Submission Date  
**Field Name:** `reg_submission_date`  
**Data Type:** date  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 4. Trading Start Retroactive
**Field Name:** `trading_start_retroactive`  
**Data Type:** date  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 5. Trading Start Proactive
**Field Name:** `trading_start_proactive`  
**Data Type:** date  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 6. Pipeline Config
**Field Name:** `pipeline_config`  
**Data Type:** unknown  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 7. Risk Scores
**Field Name:** `Risk_Scores`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 8. Inspection Recommendation
**Field Name:** `inspection_recommendation`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 9. Sent Successfully
**Field Name:** `sent_successfully`  
**Data Type:** unknown  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 10. Send Failed
**Field Name:** `send_failed`  
**Data Type:** unknown
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 11. Answer IDs
**Field Name:** `answer_ids`  
**Data Type:** unknown  
**Optional:** No  
**Source:** unknown
**Comments:** unknown

### 12. Local Council
**Field Name:** `local_council`  
**Data Type:** string  
**Optional:** No  
**Source:** unknown
**Comments:** unknown
