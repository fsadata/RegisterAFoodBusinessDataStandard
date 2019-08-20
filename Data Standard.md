# Register A Food Business Data Standard
### What Is This Document?
This document describes the data standard for Register a Food Business data collated by the Food Standards Agency from a Food Business wishing to register with their Local Authority. It describes the fields, their data types and order as well as providing specific guidance on acceptable values and which fields use specific reference data values.
This document does not describe the mechanism by which data can be submitted to the Food Standards Agency (the FSA).
### Who Is This Document For?
This document is written for two audiences. The first is for the FSA for the collation of data from Food Businesses. The second is for local authorities to inform them on how to capture food business  registration data in a consistent format.  
## What should the data look like?
The data should be supplied to the FSA as a nested JSON. An example for what the JSON should look like can be found directly bellow  
```
[{
  "id": 95,
  "fsa_rn": "ABCDEF-GHIJKL-MNOPQR",
  "council": "council-name",
  "collected": false,
  "collected_at": null,
  "createdAt": "2019-04-16T13:15:06.022Z",
  "updatedAt": "2019-04-16T13:15:06.022Z",
  "establishment": {
    "establishment_trading_name": "generic-trading-name",
    "establishment_opening_date": "2017-12-29",
    "establishment_primary_number": "01234567890",
    "establishment_secondary_number": "12345678901",
    "establishment_email": "generic@email.com",
    "operator": {
      "operator_type": "A company (registered by a representative)",
      "operator_company_name": "generic-company-name",
      "operator_company_house_number": "12345678",
      "operator_charity_name": "generic-charity-name",
      "operator_charity_number": "12345678",
      "operator_first_name": "joe",
      "operator_last_name": "blogs",
      "operator_postcode": "ab12 3cd",
      "operator_uprn": "123456789012",
      "operator_first_line": "3",
      "operator_street": "generic-road-name",
      "operator_town": "generic-town",
      "operator_primary_number": "01234567891",
      "operator_secondary_number": "01234567891",
      "operator_email": "generic@email.com",
      "contact_representative_name": "joe",
      "contact_representative_role": "blogs",
      "contact_representative_number": "01234567891",
      "contact_representative_email": "generic@email.com",
      "partners": []
    },
    "activities": {
      "customer_type": "End consumer",
      "business_type": "Greengrocer",
      "business_type_search_term": null,
      "import_export_activities": "Directly import",
      "business_other_details": "generic other business details",
      "opening_days_irregular": null,
      "opening_day_monday": false,
      "opening_day_tuesday": true,
      "opening_day_wednesday": true,
      "opening_day_thursday": false,
      "opening_day_friday": true,
      "opening_day_saturday": false,
      "opening_day_sunday": true,
    },
    "premise": {
      "establishment_first_line": "3",
      "establishment_street": "generic street",
      "establishment_town": "generic town",
      "establishment_postcode": "ab12 3cd",
      "establishment_uprn": "01234567891",
      "establishment_type": "Mobile or moveable premises",  
    }
  },
  "metadata": {
    "declaration1": "True",
    "declaration2": "True",
    "declaration3": "True",
  }
}
```  
The fields and tables in the above example json can be found in the list bellow as well as the field explanation and restrictions.  
## Fields contained within the JSON
1. [Food Business Registration](#1-food-business-registration)
2. [Food Business Reference Number](2-#food-business-reference-number)
3. [Local Authority](#3-local-authority)
4. [Record Collected By LA](#4-record-collected-by-la)
5. [Record Collected By LA At](#5-record-collected-by-la-at)
6. [Record Created At](#6-record-created-at)
7. [Record Updated At](#7-record-updated-at)
8. [Food Business Establishment](#8-food-business-establishment)
9. [Establishment Trading Name](#9-establishment-trading-name)
10. [Establishment Opening Date](#10-establishment-opening-date)
11. [Establishment Primary Telephone Number](#11-establishment-primary-telephone-number)
12. [Establishment Secondary Telephone Number](#12-establishment-secondary-telephone-number)
13. [Establishment Email Address](#13-establishment-email-address)
14. [Food Business Operator](#14-food-business-operator)
15. [Establishment Operator Type](#15-establishment-operator-type)
16. [Operator Company Name](#16-operator-company-name)
17. [Operator Companies House Reference Number](#17-operator-companies-house-reference-number)
18. [Operator Charity Name](#18-operator-charity-name)
19. [Operator Charity Number](#19-operator-charity-number)
20. [Operator First Name](#20-operator-first-name)
21. [Operator Last Name](#21-operator-last-name)
22. [Operator Postcode](#22-operator-postocde)
23. [Operator Address First Line](#23-operator-address-first-line)
24. [Operator Address Street](#24-operator-address-street)
25. [Operator Address Town](#25-operator-address-town)
26. [Operator Address UPRN](#26-operator-address-uprn)
27. [Operator Primary Telephone Number](#27-operator-primary-telephone-number)
28. [Operator Secondary Telephone Number](#28-operator-secondary-telephone-number)
29. [Operator Email Address](#29-operator-email-address)
30. [Operator Contact Representative](30-operatpr-contact-representative)
31. [Operator Contact Role](#31-operator-contact-role)
32. [Operator Contact Phone Number](#32-operator-contact-phone-number)
33. [Operator Contact Email Address](#33-operator-contact-email-address)
34. [Operator Partners](#34-operator-partners)
35. [Operator Partner Name](#35-operator-partner-name)
36. [Operator Partner Is primary Contact](#36-operator-partner-is-primary-contact)
37. [Food Business Activities](#37-food-business-activities)
38. [Customer Type](#38-customer-type)
39. [Business Type](#39-business-type)
40. [Business Type Search Term](#40-business-type-search-term)
41. [Import Export Activities](#41-import-export-activities)
42. [Water Supply](#42-water-supply)
43. [Business Other Details](#43-business-other-details)
44. [Opening Days Irregular](#44-opening-days-irregular)
45. [Opening Day Monday](#45-opening-day-monday)
46. [Opening Day Tuesday](#46-opening-day-tuesday)
47. [Opening Day Wednesday](#47-opening-day-wednesday)
48. [Opening Day Thursday](#48-opening-day-thursday)
49. [Opening Day Friday](#49-opening-day-friday)
50. [Opening Day Saturday](#50-opening-day-saturday)
51. [Opening Day Sunday](#51-opening-day-sunday)
52. [Opening Hours Monday](#52-opening-hours-monday)
53. [Opening Hours Tuesday](#53-opening-hours-tuesday)
54. [Opening Hours Wednesday](54-opening-hours-wednesday)
55. [Opening Hours Thursday](#55-opening-hours-thursday)
56. [Opening Hours Friday](#56-opening-hours-friday)
57. [Opening Hours Saturday](#57-opening-hours-saturday)
58. [Opening Hours Sunday](#58-opening-hours-sunday)
59. [Food Business Premises](#59-food-business-premises)
60. [Establishment Address First Line](#60-estabishment-address-first-line)
61. [Establishment Address Street](#61-establishment-address-street)
62. [Establishment Address Town](#62-establishment-address-town)
63. [Establishment Address Postcode](63-estabishment-address-postcode)
64. [Establishment Address UPRN](#64-estabishment-address-uprb)
65. [Establishment Type](#65-estabishment-type)
66. [Declaration](#66-declaration)
67. [Declaration 1](#67-declaration-1)
68. [Declaration 2](#68-declaration-2)
69. [Declaration 3](#69-declaration-3)  

## Details  

### 1. Food Business Registration
**JSON Name:** `registration`  
**Data Type and Size:** Data structure  
**Description of Field and Reason for Collection:** The top-level data structure for a single registration  
**Source of Data:**  
**Validation Rules:**  
**Validation Implemented in RAFB:**  
**Data Example:**  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y    
### 2. Food Business Reference Number
**JSON Name:** `fsa_rn`  
**Data Type and Size:** String (20)  
**Description of Field and Reason for Collection:** "Food Standards Agency transaction Reference Number.  Uniquely identifies an application to register a food business establishment,  
**Source of Data:** "Generated by calling the FSA-RN micorservice at https://fsa-reference-numbers.epimorphics.net/generate/ {councilCode}/{typeCode}  
where:  
councilCode represents the local authority code in the register of competent authorities at: https://data.food.gov.uk/codes/reference-number/_authority  
typeCode is 001 production or 000 dev/test"  
**Validation Rules:** Must be present in a food business registration record.  
**Validation Implemented in RAFB:** Not applicable - generated within RAFB.  
**Data Example:** AHFGHL-CNFVJQ-D6H8BH  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 3. Local Authority
**JSON Name:** `council`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Local Authority name.  
This is configuration data that originates from the register of competent authorities https://data.food.gov.uk/codes/reference-number/_authority"  
**Source of Data:** Generated as configuration data within the registration application.    
**Validation Rules:** Must be present in a food business registration record.  
**Validation Implemented in RAFB:** Must be present in a food business registration record.  
**Data Example:** "Vale of Glamorgan Council
Mid Ulster District Council"  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):**  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  

### 4. Record Collected By LA
**JSON Name:** `collected`  
**Data Type and Size:** boolean  
**Description of Field and Reason for Collection:** "true if registration has been collected
false if registration has not been collected."  
**Source of Data:** Set via PUT method in the RAFB collections API called by external LA MIS application.  
**Validation Rules:** "Default value is false.
Can be set to true or false"  
**Validation Implemented in RAFB:** Can only be set to true or false  
**Data Example:** true, false  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 5. Record Collected By LA At
**JSON Name:** `collected_at`  
**Data Type and Size:** ISO date time  
**Description of Field and Reason for Collection:** Date time of collection of registration.  
**Source of Data:** Generated within the registration application.  
**Validation Rules:** Will contain a value if the collected flag has been set (or reset).  
**Validation Implemented in RAFB:** Must be datetime value.  
**Data Example:** 2019-04-16T13:15:06.022Z  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 6. Record Created At
**JSON Name:** `createdAt`  
**Data Type and Size:** ISO date time  
**Description of Field and Reason for Collection:** "Date time this record created.
"  
**Source of Data:** Generated within the registration application.  
**Validation Rules:** Must be set.  
**Validation Implemented in RAFB:** Set by RAFB application.  
**Data Example:** 2019-04-16T13:15:06.022Z  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 7. Record Updated At
**JSON Name:** `updatedAt`  
**Data Type and Size:** ISO date time  
**Description of Field and Reason for Collection:** "date time most recent update of record.
Generated by the application."  
**Source of Data:** Generated within the registration application.  
**Validation Rules:** Will only be set if record has been updated after creation.  
**Validation Implemented in RAFB:** Set by RAFB application.  
**Data Example:** 2019-04-16T13:15:06.022Z  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 8. Food Business Establishment
**JSON Name:** `establishment`  
**Data Type and Size:** Data structure  
**Description of Field and Reason for Collection:** This data structure contains the establishment details, operator, premises and business activity information within the registration.  
**Source of Data:**  
**Validation Rules:**  
**Validation Implemented in RAFB:**  
**Data Example:**  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 9. Establishment Trading Name
**JSON Name:** `establishment_trading_name`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Proposed trading name of the new food business.  
Collection allows comparison of RAFB and FHRS data.
"  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be provided in this data set.  
**Validation Implemented in RAFB:** ASCII string  
**Data Example:** Tropical Pizzas  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 10. Establishment Opening Date
**JSON Name:** `establishment_opening_date`  
**Data Type and Size:** ISO8061 date  
**Description of Field and Reason for Collection:** Opening date of the food business.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Opening date or estimating opening date must be provided.  
**Validation Implemented in RAFB:** "ISO Date String
npm validator isISO8601"  
**Data Example:** 2017-12-29  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 11. Establishment Primary Telephone Number
**JSON Name:** `establishment_primary_number`  
**Data Type and Size:** String (15)  
**Description of Field and Reason for Collection:** Primary telephone number of the food business.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Valid phone number must be provided.  
**Validation Implemented in RAFB:** "Numeric string
Between 5 and 20 characters (5 < x < 20)
Allows ""blank space"" and ""+"" "  
**Data Example:** "02921455657  
029 21455657
"  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 12. Establishment Secondary Telephone Number
**JSON Name:** `establishment_secondary_number`  
**Data Type and Size:** String (15)  
**Description of Field and Reason for Collection:** Primary telephone number of the food business.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Optional, must be a valid phone number if provided.  
**Validation Implemented in RAFB:** "Numeric string
Between 5 and 20 characters (5 < x < 20)
Allows ""blank space"" and ""+"" "  
**Data Example:** "07976765432  
+4435021022345"  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 13. Establishment Email Address
**JSON Name:** `establishment_email`  
**Data Type and Size:** String (254)  
**Description of Field and Reason for Collection:** Email address of the food business establishment.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Valid email address must be provided.  
**Validation Implemented in RAFB:** "String,
npm validator isEmail"  
**Data Example:** orders@tropical-pizzas.co.uk  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 15. Food Business Operator
**JSON Name:** `operator`  
**Data Type and Size:** Data structure  
**Description of Field and Reason for Collection:** This data structure contains the operator type and details  
**Source of Data:**  
**Validation Rules:**  
**Validation Implemented in RAFB:**  
**Data Example:**  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 15. Establishment Operator Type
**JSON Name:** `operator_type`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** "Type of food business operator - sole trader, partnership, limited company, person or charity.  
The answer to this question determines the data captured for the operator of the establishment."  
**Source of Data:** Chosen by the food business operator user.  
**Validation Rules:** "One of five fixed values must be present.  
Sole Trader: Sole trader  
Partnership: Partnership  
Limited Company: A company (registered by a representative)  
Person: A person (registered by a representative)  
Charity: A charity (registered by a representative)"  
**Validation Implemented in RAFB:** Radio button selection in RAFB.  
**Data Example:** "Sole trader  
A company (registered by a representative)"  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 16. Operator Company Name
**JSON Name:** `operator_company_name`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** Limited Company only: Company name.  Data entered by the food business operator user.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present when operator type is Limited Company.  
**Validation Implemented in RAFB:** String.  
**Data Example:** Tropical Pizzas South Wales Limited  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 17. Operator Companies House Reference Number
**JSON Name:** `operator_company_house_number`  
**Data Type and Size:** String (8)  
**Description of Field and Reason for Collection:** Limited Company only: Companies House number.  Data entered by the food business operator user.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present when operator type is Limited Company.  
**Validation Implemented in RAFB:** "String
npm validator isAlphanumeric (GB)
8 Characters in length
First two characters numeric"  
**Data Example:** 3875473  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 18. Operator Charity Name
**JSON Name:** `operator_charity_name`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Charity only: Charity Name.  
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present when operator type is Charity.  
**Validation Implemented in RAFB:** String.  
**Data Example:** Fred Wills Trust  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 19. Operator Charity Number
**JSON Name:** `operator_charity_number`  
**Data Type and Size:** String (8)  
**Description of Field and Reason for Collection:** "Charity only: Charity Registration Number.  
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present when operator type is Charity.  
**Validation Implemented in RAFB:** "String
Allows ""-""
Between 6 to 8 characters in length (6 < x < 8)
npm validator isAlphanumeric (GB)"  
**Data Example:** 10028465  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 20. Operator First Name
**JSON Name:** `operator_first_name`  
**Data Type and Size:** String (70)  
**Description of Field and Reason for Collection:** "Sole Trader, Person: Operator First Name.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present when operator type is Person or Sole Trader.  
**Validation Implemented in RAFB:** String.  
**Data Example:** Julian  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 21. Operator Last Name
**JSON Name:** `operator_last_name`  
**Data Type and Size:** String (70)  
**Description of Field and Reason for Collection:** "Sole Trader, Person: Operator Last Name.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present when operator type is Person or Sole Trader.  
**Validation Implemented in RAFB:** String.  
**Data Example:** Wills  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 22. Operator Postcode
**JSON Name:** `operator_postcode`  
**Data Type and Size:** String (8)  
**Description of Field and Reason for Collection:** "Postcode of the operator address.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** "String
npm validator isPostalCode (GB)
"  
**Data Example:** CF23 5AT  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 23. Operator Address First Line
**JSON Name:** `operator_first_line`  
**Data Type and Size:** String (70)  
**Description of Field and Reason for Collection:** First line (or street number) of operator address.  Data entered by the food business operator user.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** 241  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 24. Operator Address Street
**JSON Name:** `operator_street`  
**Data Type and Size:** String (256)  
**Description of Field and Reason for Collection:** "Street Name of operator address.
Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** Southminster Road  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 25. Operator Address Town
**JSON Name:** `operator_town`  
**Data Type and Size:** String (256)  
**Description of Field and Reason for Collection:** "Town of operator address.
Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** "Must be present.
"  
**Validation Implemented in RAFB:** "ASCII String.
"  
**Data Example:** Cardiff  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 26. Operator Address UPRN
**JSON Name:** `operator_uprn`  
**Data Type and Size:** String (12)  
**Description of Field and Reason for Collection:** "UPRN (Unique Property Reference Number) of the operator address.
Data retrieved from the address record supplied by API call to the Postcoder service."  
**Source of Data:** Data generated from the postcode lookup and validation API calls.  
**Validation Rules:** Highly desirable to be present.  May be missing in edge cases where address was not found in postcode lookup.  
**Validation Implemented in RAFB:** Not applicable - generated during postcode lookup.  
**Data Example:** 520887636906  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 27. Operator Primary Telephone Number
**JSON Name:** `operator_primary_number`  
**Data Type and Size:** String (15)  
**Description of Field and Reason for Collection:** "Operator primary phone number.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Valid phone number must be provided.  
**Validation Implemented in RAFB:** "Numeric string
Between 5 and 20 characters (5 < x < 20)
Allows ""blank space"" and ""+"" "  
**Data Example:** "02921455657  
029 21455657
"  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 28. Operator Secondary Telephone Number
**JSON Name:** `operator_secondary_number`  
**Data Type and Size:** String (15)  
**Description of Field and Reason for Collection:** "Operator secondary phone number.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Optional, must be a valid phone number if provided.  
**Validation Implemented in RAFB:** "Numeric string
Between 5 and 20 characters (5 < x < 20)
Allows ""blank space"" and ""+"" "  
**Data Example:** "07976765432  
+4435021022345"  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 29. Operator Email Address
**JSON Name:** `operator_email`  
**Data Type and Size:** String (254)  
**Description of Field and Reason for Collection:** "Email address of the food business operator.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Valid email address must be provided.  
**Validation Implemented in RAFB:** "String,
npm validator isEmail"  
**Data Example:** orders@tropical-pizzas.co.uk  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 30. Operator Contact Representative
**JSON Name:** `contact_representative_name`  
**Data Type and Size:** String (70)  
**Description of Field and Reason for Collection:** "Name of person representing the food business operator.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If Business Type is Limited Company or Charity then must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** John Smith  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 31. Operator Contact Role
**JSON Name:** `contact_representative_role`  
**Data Type and Size:** String (256)  
**Description of Field and Reason for Collection:** "Role of the person representing the food business operator.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If Business Type is Limited Company or Charity then must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** Restaurant Manager  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 32. Operator Contact Phone Number
**JSON Name:** `contact_representative_number`  
**Data Type and Size:** String (15)  
**Description of Field and Reason for Collection:** "Phone number for the person representing the food business operator.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** 7976765432  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 33. Operator Contact Email Address
**JSON Name:** `contact_representative_email`  
**Data Type and Size:** String (254)  
**Description of Field and Reason for Collection:** "Email address for the person representing the food business operator.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** julian@tropical-pizzas.co.uk  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 34. Operator Partners
**JSON Name:** `partners`  
**Data Type and Size:** Array  
**Description of Field and Reason for Collection:** "Array of partner data – containing sets of between two and five partner_name and partner_is_primary_contact data fields.  
Currently limited to the first five partners (noting that some partnerships have more than this).  One partner_is_primary_contact field will have value true and the others will have value false."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** "Must be present when operator type is Partnership.
"  
**Validation Implemented in RAFB:** "Array must contain between 2 and 5 partners.  
One partner only must be the primary contact."  
**Data Example:**  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 35. [Operator Partner Name](#35-operator-partner-name)
**JSON Name:** `partner_name`  
**Data Type and Size:** String (56)  
**Description of Field and Reason for Collection:** Partner name as entered by the food business operator user.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present for a specific partner.  
**Validation Implemented in RAFB:** String.  
**Data Example:** "Joan Smith  
John Edward Smith"  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 36. [Operator Partner Is primary Contact](#36-operator-partner-is-primary-contact)
**JSON Name:** `partner_is_primary_contact`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** "Selected by the food business operator user.  true means the partner is the primary contact for this registration, and false means the partner is not the primary contact.  
Partnerships may have more than five partners, in which case only the first five can be entered, this must include a partner acting as primary contact for further enquiries."  
**Source of Data:** Data entered by the food business operator user as a choice against each partner entered.  
**Validation Rules:** Must be set for each partner in the partner array.  One partner must be set to true and all others present must be false.  
**Validation Implemented in RAFB:** Not applicable - set by user choice of radio button in the RAFB application.  
**Data Example:** "true  
false"  
**Personal Data (Y/N):**  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 37. Food Business Activities
**JSON Name:** `activities`  
**Data Type and Size:** Data structure  
**Description of Field and Reason for Collection:** This data structure describes the activities of the food business  
**Source of Data:**  
**Validation Rules:**  
**Validation Implemented in RAFB:**  
**Data Example:**  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 38. Customer Type
**JSON Name:** `customer_type`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** Food business operator user selects the type of customers served by the food business.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** "Must be one of the following three values.
End consumer,
Other businesses,
End consumer and other businesses."  
**Validation Implemented in RAFB:** One of the values in the Customer Type list must be selected.  
**Data Example:** "End consumer  
Other businesses"  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 39. Business Type
**JSON Name:** `business_type`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** "Type of food business as selected by the food business operator from a predefined list.  
"  
**Source of Data:** Data selection made by the food business operator user from a predefined list.  
**Validation Rules:** Must be present and must be validated against the code list for Business types which is loaded from this file in GitHub https://github.com/FoodStandardsAgency/register-a-food-business-front-end/blob/master/src/components/business-type-transformed.json  as the displayName field.  
**Validation Implemented in RAFB:** One of the values in the Business Type list must be selected.  
**Data Example:** "Livestock farm  
Greengrocer  
Shellfish purification centre  
Commercial bakery  
Alcoholic drinks manufacturer
"  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 40. Business Type Search Term
**JSON Name:** `business_type_search_term`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** "Search term used by the food business operator user to find a business_type.   This is a predefined list that maps business_type_search_term values to a specific business_type  
Field mapping is stored in the data loaded from GitHub https://github.com/FoodStandardsAgency/register-a-food-business-front-end/blob/master/src/components/business-type-transformed.json"  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Optional part of the data set used to help identify a Business Type.  
**Validation Implemented in RAFB:** One of the values in the Business Type Search Term list must be selected.  
**Data Example:** "Pig
Bee
Tilapia
Halal"  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 41. Import Export Activities
**JSON Name:** `import_export_activities`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** "Food business operator user selects the type of import and export activity from four choices.
None,
Directly import,
Directly export,
Directly import and export"  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present  
**Validation Implemented in RAFB:** Not applicable - radio button selection in application.  
**Data Example:** Directly import and export  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 42. Water Supply
**JSON Name:** `water_supply`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** "Selected by the food business operator user from the following values: Public, Private,
Private and public."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** "Must be one of the following values: Public, Private,
Private and public."  
**Validation Implemented in RAFB:** Not applicable - user choice captured by RAFB application.  
**Data Example:** "Private  
Private and public"  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 43. Business Other Details
**JSON Name:** `business_other_details`  
**Data Type and Size:** String (150)  
**Description of Field and Reason for Collection:** Additional information that the food business operator user may enter to accurately describe what the business does.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Optional information.  
**Validation Implemented in RAFB:** String.  
**Data Example:** Shop making artisan chocolates in Greenwich  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 44. Opening Days Irregular
**JSON Name:** `opening_days_irregular`  
**Data Type and Size:** String (1500)  
**Description of Field and Reason for Collection:** "Descriptive text entered by food business operator user to describe irregular opening days.  
"  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Either opening_days_irregular has a value or the opening_day_monday through opening_day_sunday fields all have values.  
**Validation Implemented in RAFB:** String.  
**Data Example:** Irregular evenings when football match is held  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 45. Opening Day Monday
**JSON Name:** `opening_day_monday`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** Selected by food business operator user.  true if open this day, false if not.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Either opening_days_irregular has a value or the opening_day_monday through opening_day_sunday fields all have values.  
**Validation Implemented in RAFB:** When used, set within RAFB application to true or false.  
**Data Example:** true, false  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 46. Opening Day Tuesday
**JSON Name:** `opening_day_tuesday`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** Selected by food business operator user.  true if open this day, false if not.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:**  
**Validation Implemented in RAFB:** When used, set within RAFB application to true or false.  
**Data Example:** true, false  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 47. Opening Day Wednesday
**JSON Name:** `opening_day_wednesday`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** Selected by food business operator user.  true if open this day, false if not.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:**  
**Validation Implemented in RAFB:** When used, set within RAFB application to true or false.  
**Data Example:** true, false  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 48. Opening Day Thursday
**JSON Name:** `opening_day_thursday`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** Selected by food business operator user.  true if open this day, false if not.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:**  
**Validation Implemented in RAFB:** When used, set within RAFB application to true or false.  
**Data Example:** true, false  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 49. Opening Day Friday
**JSON Name:** `opening_day_friday`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** Selected by food business operator user.  true if open this day, false if not.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:**  
**Validation Implemented in RAFB:** When used, set within RAFB application to true or false.  
**Data Example:** true, false  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 50. Opening Day Saturday
**JSON Name:** `opening_day_saturday`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** Selected by food business operator user.  true if open this day, false if not.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:**  
**Validation Implemented in RAFB:** When used, set within RAFB application to true or false.  
**Data Example:** true, false  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 51. Opening Day Sunday
**JSON Name:** `opening_day_sunday`  
**Data Type and Size:** Boolean  
**Description of Field and Reason for Collection:** Selected by food business operator user.  true if open this day, false if not.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:**  
**Validation Implemented in RAFB:** When used, set within RAFB application to true or false.  
**Data Example:** true, false  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 52. Opening Hours Monday
**JSON Name:** `opening_hours_monday`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Free text description of the Monday opening hours of the food business establishment.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If opening_hours_monday is true then a value must be present.  
**Validation Implemented in RAFB:** String.  
**Data Example:** 09:00-12:30 13:00-18+L55:L61:00  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 53. Opening Hours Tuesday
**JSON Name:** `opening_hours_tuesday`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Free text description of the Tuesday opening hours of the food business establishment.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If opening_hours_tuesday is true then a value must be present.  
**Validation Implemented in RAFB:** String.  
**Data Example:** 09:00-12:30 13:00-18:00  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 54. Opening Hours Wednesday
**JSON Name:** `opening_hours_wednesday`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Free text description of the Wednesday opening hours of the food business establishment.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If opening_hours_wednesday is true then a value must be present.  
**Validation Implemented in RAFB:** String.  
**Data Example:** 09:00-12:30  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 55. Opening Hours Thursday
**JSON Name:** `opening_hours_thursday`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Free text description of the Thursday opening hours of the food business establishment.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If opening_hours_thursday is true then a value must be present.  
**Validation Implemented in RAFB:** String.  
**Data Example:** 09:00-12:30 13:00-18:00  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 56. Opening Hours Friday
**JSON Name:** `opening_hours_friday`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Free text description of the Friday opening hours of the food business establishment.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If opening_hours_friday is true then a value must be present.  
**Validation Implemented in RAFB:** String.  
**Data Example:** 09:00-12:30 13:00-18:00  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 57. Opening Hours Saturday
**JSON Name:** `opening_hours_saturday`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Free text description of the Saturday opening hours of the food business establishment.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If opening_hours_saturday is true then a value must be present.  
**Validation Implemented in RAFB:** String.  
**Data Example:** 10:00-18:00  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 58. Opening Hours Sunday
**JSON Name:** `opening_hours_sunday`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Free text description of the Sunday opening hours of the food business establishment.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** If opening_hours_sunday is true then a value must be present.  
**Validation Implemented in RAFB:** String.  
**Data Example:** 10:30-16:30  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 59. Food Business Premises
**JSON Name:** `premise`  
**Data Type and Size:** Data structure  
**Description of Field and Reason for Collection:** This data structure conatins data on the food business premises  
**Source of Data:**  
**Validation Rules:**  
**Validation Implemented in RAFB:**  
**Data Example:**  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 60. Establishment Address First Line
**JSON Name:** `establishment_first_line`  
**Data Type and Size:** String (256)  
**Description of Field and Reason for Collection:** "First line (or street number) of the food business establishment address.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** 612  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 61. Establishment Address Street
**JSON Name:** `establishment_street`  
**Data Type and Size:** String (256)  
**Description of Field and Reason for Collection:** "Street Name of the food business establishment address.
Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** Newport Road  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 62. Establishment Address Town
**JSON Name:** `establishment_town`  
**Data Type and Size:** String (256)  
**Description of Field and Reason for Collection:** "Town of the food business establishment address.
Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** ASCII String.  
**Data Example:** Cardiff  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 63. Establishment Address Postcode
**JSON Name:** `establishment_postcode`  
**Data Type and Size:** String (8)  
**Description of Field and Reason for Collection:** "Postcode of the food business establishment address.
Data entered by the food business operator user."  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** "String
npm validator isPostalCode (GB)"  
**Data Example:** CF99 6TR  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 64. Establishment Address UPRN
**JSON Name:** `establishment_uprn`  
**Data Type and Size:** String (12)  
**Description of Field and Reason for Collection:** UPRN (Unique Property Reference Number) of the food business establishment address.  Data retrieved from the address record supplied by API call to the Postcoder service.  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Highly desirable to be present.  May be missing in edge cases where address was not found in postcode lookup.  
**Validation Implemented in RAFB:** Not applicable - generated during postcode lookup.  
**Data Example:** 824683234325  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** N  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 65. Establishment Type
**JSON Name:** `establishment_type`  
**Data Type and Size:** String (50)  
**Description of Field and Reason for Collection:** "Selected by the food business operator user from three options.  
Place of business or commercial premises  
Mobile or moveable premises  
Home or domestic premises"  
**Source of Data:** Data entered by the food business operator user.  
**Validation Rules:** Must be present.  
**Validation Implemented in RAFB:** Not applicable - selected via radio button in application.  
**Data Example:** Mobile or moveable premises  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 66. Declaration
**JSON Name:** `metadata`  
**Data Type and Size:** "A data structure in the data set that contains the declaration data fields.  This structure is likely to be removed in a future release and the declaration data fields placed in the top-level registrations structure.
"  
**Description of Field and Reason for Collection:**  
**Source of Data:**  
**Validation Rules:**  
**Validation Implemented in RAFB:**  
**Data Example:**  
**Personal Data (Y/N):** N  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):** Y  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 67. Declaration 1
**JSON Name:** `declaration1`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** Food business operator user must tick agreement to this preset declaration.  
**Source of Data:** Food business operator user ticks box to confirm that they agree to this statement.  
**Validation Rules:** Declaration text must be present in a food business registration record.  
**Validation Implemented in RAFB:** User agreement captured in RAFB application.  
**Data Example:** I declare that the information I have given on this form is correct and complete to the best of my knowledge and belief.  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):**  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 68. Declaration 2
**JSON Name:** `declaration2`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** Food business operator user must tick agreement to this preset declaration.  
**Source of Data:** Food business operator user ticks box to confirm that they agree to this statement.  
**Validation Rules:** Declaration text must be present in a food business registration record.  
**Validation Implemented in RAFB:** User agreement captured in RAFB application.  
**Data Example:** The operator will notify their LA of any significant changes to the business activity, including closure, within 28 days of the change happening.  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):**  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
### 69. Declaration 3
**JSON Name:** `declaration3`  
**Data Type and Size:** String  
**Description of Field and Reason for Collection:** Food business operator user must tick agreement to this preset declaration.  
**Source of Data:** Food business operator user ticks box to confirm that they agree to this statement.  
**Validation Rules:** Declaration text must be present in a food business registration record.  
**Validation Implemented in RAFB:** User agreement captured in RAFB application.  
**Data Example:** The operator understands they are legally responsible for the safety and authenticity of the food being produced or served at this establishment.  
**Personal Data (Y/N):** Y  
**Stored in RAFB temporary data store (Y/N):** Y  
**Data Sent to LA in Notification Emails (Y/N):**  
**Collected by Unified View Y/N):** Y  
**Collected by LA Y/N):** Y  
## Table Layout
If you would prefer the information above is also available as a table  

| field name | JSON Name | Data Type and Size | Description of Field and Reason for Collection | Source of Data | Validation Rules | Validation Implemented in RAFB | Data Example | Personal Data \(Y/N\) | Stored in RAFB temporary data store \(Y/N\) | Data Sent to LA in Notification Emails \(Y/N\) | Collected by Unified View Y/N\) | Collected by LA Y/N\) |
|-------------------------------------------|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|---------------------------------------------|------------------------------------------------|---------------------------------|-----------------------|
| Food Business Registration | registration | Data structure | The top\-level data structure for a single registration | Y | Y | N | Y | Y |
| Food Business Reference Number | fsa\_rn | String \(20\) | Food Standards Agency transaction Reference Number\. Uniquely identifies an application to register a food business establishment, | Generated by calling the FSA\-RN micorservice at https://fsa\-reference\-numbers\.epimorphics\.net/generate/ \{councilCode\}/\{typeCode\} where: councilCode represents the local authority code in the register of competent authorities at: https://data\.food\.gov\.uk/codes/reference\-number/\_authority typeCode is 001 production or 000 dev/test | Must be present in a food business registration record\. | Not applicable \- generated within RAFB\. | AHFGHL\-CNFVJQ\-D6H8BH | N | Y | Y | Y | Y |
| Local Authority | council | String \(50\) | Local Authority name\. This is configuration data that originates from the register of competent authorities https://data\.food\.gov\.uk/codes/reference\-number/\_authority | Generated as configuration data within the registration application\. | Must be present in a food business registration record\. | Must be present in a food business registration record\. | Vale of Glamorgan Council Mid Ulster District Council | Y | Y | Y |
| Record Collected By LA | collected | boolean | true if registration has been collected false if registration has not been collected\. | Set via PUT method in the RAFB collections API called by external LA MIS application\. | Default value is false\. Can be set to true or false | Can only be set to true or false | true, false | Y | N | Y | Y |
| Record Collected By LA At | collected\_at | ISO date time | Date time of collection of registration\. | Generated within the registration application\. | Will contain a value if the collected flag has been set \(or reset\)\. | Must be datetime value\. | 2019\-04\-16T13:15:06\.022Z | Y | N | Y | Y |
| Record Created At | createdAt | ISO date time | Date time this record created\. | Generated within the registration application\. | Must be set\. | Set by RAFB application\. | 2019\-04\-16T13:15:06\.022Z | Y | N | Y | Y |
| Record Updated At | updatedAt | ISO date time | date time most recent update of record\. Generated by the application\. | Generated within the registration application\. | Will only be set if record has been updated after creation\. | Set by RAFB application\. | 2019\-04\-16T13:15:06\.022Z | Y | N | Y | Y |
| Food Business Establishment | establishment | Data structure | This data structure contains the establishment details, operator, premises and business activity information within the registration\. | Y | N | Y | Y |
| Establishment Trading Name | establishment\_trading\_name | String \(50\) | Proposed trading name of the new food business\. Collection allows comparison of RAFB and FHRS data\. | Data entered by the food business operator user\. | Must be provided in this data set\. | ASCII string | Tropical Pizzas | N | Y | Y | Y | Y |
| Establishment Opening Date | establishment\_opening\_date | ISO8061 date | Opening date of the food business\. | Data entered by the food business operator user\. | Opening date or estimating opening date must be provided\. | ISO Date String npm validator isISO8601 | 2017\-12\-29 | N | Y | Y | Y | Y |
| Establishment Primary Telephone Number | establishment\_primary\_number | String \(15\) | Primary telephone number of the food business\. | Data entered by the food business operator user\. | Valid phone number must be provided\. | Numeric string Between 5 and 20 characters \(5 < x < 20\) Allows "blank space" and "\+" | 02921455657 029 21455657 | Y | Y | Y | Y | Y |
| Establishment Secondary Telephone Number | establishment\_secondary\_number | String \(15\) | Primary telephone number of the food business\. | Data entered by the food business operator user\. | Optional, must be a valid phone number if provided\. | Numeric string Between 5 and 20 characters \(5 < x < 20\) Allows "blank space" and "\+" | 07976765432 \+4435021022345 | Y | Y | Y | Y | Y |
| Establishment Email Address | establishment\_email | String \(254\) | Email address of the food business establishment\. | Data entered by the food business operator user\. | Valid email address must be provided\. | String, npm validator isEmail | orders@tropical\-pizzas\.co\.uk | Y | Y | Y | Y | Y |
| Food Business Operator | operator | Data structure | This data structure contains the operator type and details | Y | Y | N | Y | Y |
| Establishment Operator Type | operator\_type | String | Type of food business operator \- sole trader, partnership, limited company, person or charity\. The answer to this question determines the data captured for the operator of the establishment\. | Chosen by the food business operator user\. | One of five fixed values must be present\. Sole Trader: Sole trader Partnership: Partnership Limited Company: A company \(registered by a representative\) Person: A person \(registered by a representative\) Charity: A charity \(registered by a representative\) | Radio button selection in RAFB\. | Sole trader A company \(registered by a representative\) | N | Y | Y | Y | Y |
| Operator Company Name | operator\_company\_name | String \(50\) | Limited Company only: Company name\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present when operator type is Limited Company\. | String\. | Tropical Pizzas South Wales Limited | Y | Y | Y | Y | Y |
| Operator Companies House Reference Number | operator\_company\_house\_number | String \(8\) | Limited Company only: Companies House number\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present when operator type is Limited Company\. | String npm validator isAlphanumeric \(GB\) 8 Characters in length First two characters numeric | 3875473 | Y | Y | Y | Y | Y |
| Operator Charity Name | operator\_charity\_name | String \(50\) | Charity only: Charity Name\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present when operator type is Charity\. | String\. | Fred Wills Trust | Y | Y | Y | Y | Y |
| Operator Charity Number | operator\_charity\_number | String \(8\) | Charity only: Charity Registration Number\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present when operator type is Charity\. | String Allows "\-" Between 6 to 8 characters in length \(6 < x < 8\) npm validator isAlphanumeric \(GB\) | 10028465 | Y | Y | Y | Y | Y |
| Operator First Name | operator\_first\_name | String \(70\) | Sole Trader, Person: Operator First Name\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present when operator type is Person or Sole Trader\. | String\. | Julian | Y | Y | Y | Y |
| Operator Last Name | operator\_last\_name | String \(70\) | Sole Trader, Person: Operator Last Name\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present when operator type is Person or Sole Trader\. | String\. | Wills | Y | Y | Y | Y |
| Operator Postcode | operator\_postcode | String \(8\) | Postcode of the operator address\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | String npm validator isPostalCode \(GB\) | CF23 5AT | Y | Y | Y | Y |
| Operator Address First Line | operator\_first\_line | String \(70\) | First line \(or street number\) of operator address\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | 241 | Y | Y | Y | Y |
| Operator Address Street | operator\_street | String \(256\) | Street Name of operator address\. Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | Southminster Road | Y | Y | Y | Y |
| Operator Address Town | operator\_town | String \(256\) | Town of operator address\. Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | Cardiff | Y | Y | Y | Y |
| Operator Address UPRN | operator\_uprn | String \(12\) | UPRN \(Unique Property Reference Number\) of the operator address\. Data retrieved from the address record supplied by API call to the Postcoder service\. | Data generated from the postcode lookup and validation API calls\. | Highly desirable to be present\. May be missing in edge cases where address was not found in postcode lookup\. | Not applicable \- generated during postcode lookup\. | 520887636906 | Y | N | Y | Y |
| Operator Primary Telephone Number | operator\_primary\_number | String \(15\) | Operator primary phone number\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Valid phone number must be provided\. | Numeric string Between 5 and 20 characters \(5 < x < 20\) Allows "blank space" and "\+" | 02921455657 029 21455657 | Y | Y | Y | Y |
| Operator Secondary Telephone Number | operator\_secondary\_number | String \(15\) | Operator secondary phone number\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Optional, must be a valid phone number if provided\. | Numeric string Between 5 and 20 characters \(5 < x < 20\) Allows "blank space" and "\+" | 07976765432 \+4435021022345 | Y | Y | Y | Y |
| Operator Email Address | operator\_email | String \(254\) | Email address of the food business operator\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Valid email address must be provided\. | String, npm validator isEmail | orders@tropical\-pizzas\.co\.uk | Y | Y | Y | Y |
| Operator Contact Representative | contact\_representative\_name | String \(70\) | Name of person representing the food business operator\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If Business Type is Limited Company or Charity then must be present\. | ASCII String\. | John Smith | Y | Y | Y | Y |
| Operator Contact Role | contact\_representative\_role | String \(256\) | Role of the person representing the food business operator\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If Business Type is Limited Company or Charity then must be present\. | ASCII String\. | Restaurant Manager | Y | Y | Y | Y |
| Operator Contact Phone Number | contact\_representative\_number | String \(15\) | Phone number for the person representing the food business operator\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | 7976765432 | Y | Y | Y | Y |
| Operator Contact Email Address | contact\_representative\_email | String \(254\) | Email address for the person representing the food business operator\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | julian@tropical\-pizzas\.co\.uk | Y | Y | Y | Y |
| Operator Partners | partners | Array | Array of partner data – containing sets of between two and five partner\_name and partner\_is\_primary\_contact data fields\. Currently limited to the first five partners \(noting that some partnerships have more than this\)\. One partner\_is\_primary\_contact field will have value true and the others will have value false\. | Data entered by the food business operator user\. | Must be present when operator type is Partnership\. | Array must contain between 2 and 5 partners\. One partner only must be the primary contact\. | Y | Y | Y | Y | Y |
| Operator Partner Name | partner\_name | String \(56\) | Partner name as entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present for a specific partner\. | String\. | Joan Smith John Edward Smith | Y | Y | Y | Y |
| Operator Partner Is primary Contact | partner\_is\_primary\_contact | Boolean | Selected by the food business operator user\. true means the partner is the primary contact for this registration, and false means the partner is not the primary contact\. Partnerships may have more than five partners, in which case only the first five can be entered, this must include a partner acting as primary contact for further enquiries\. | Data entered by the food business operator user as a choice against each partner entered\. | Must be set for each partner in the partner array\. One partner must be set to true and all others present must be false\. | Not applicable \- set by user choice of radio button in the RAFB application\. | true false | Y | Y | Y | Y |
| Food Business Activities | activities | Data structure | This data structure describes the activities of the food business | Y | Y | N | Y | Y |
| Customer Type | customer\_type | String | Food business operator user selects the type of customers served by the food business\. | Data entered by the food business operator user\. | Must be one of the following three values\. End consumer, Other businesses, End consumer and other businesses\. | One of the values in the Customer Type list must be selected\. | End consumer Other businesses | N | Y | Y | Y | Y |
| Business Type | business\_type | String | Type of food business as selected by the food business operator from a predefined list\. | Data selection made by the food business operator user from a predefined list\. | Must be present and must be validated against the code list for Business types which is loaded from this file in GitHub https://github\.com/FoodStandardsAgency/register\-a\-food\-business\-front\-end/blob/master/src/components/business\-type\-transformed\.json as the displayName field\. | One of the values in the Business Type list must be selected\. | Livestock farm Greengrocer Shellfish purification centre Commercial bakery Alcoholic drinks manufacturer | N | Y | Y | Y | Y |
| Business Type Search Term | business\_type\_search\_term | String | Search term used by the food business operator user to find a business\_type\. This is a predefined list that maps business\_type\_search\_term values to a specific business\_type Field mapping is stored in the data loaded from GitHub https://github\.com/FoodStandardsAgency/register\-a\-food\-business\-front\-end/blob/master/src/components/business\-type\-transformed\.json | Data entered by the food business operator user\. | Optional part of the data set used to help identify a Business Type\. | One of the values in the Business Type Search Term list must be selected\. | Pig Bee Tilapia Halal | N | Y | N | Y | Y |
| Import Export Activities | import\_export\_activities | String | Food business operator user selects the type of import and export activity from four choices\. None, Directly import, Directly export, Directly import and export | Data entered by the food business operator user\. | Must be present | Not applicable \- radio button selection in application\. | Directly import and export | N | Y | Y | Y | Y |
| Water Supply | water\_supply | String | Selected by the food business operator user from the following values: Public, Private, Private and public\. | Data entered by the food business operator user\. | Must be one of the following values: Public, Private, Private and public\. | Not applicable \- user choice captured by RAFB application\. | Private Private and public | N | Y | Y | Y | Y |
| Business Other Details | business\_other\_details | String \(150\) | Additional information that the food business operator user may enter to accurately describe what the business does\. | Data entered by the food business operator user\. | Optional information\. | String\. | Shop making artisan chocolates in Greenwich | N | Y | Y | Y | Y |
| Opening Days Irregular | opening\_days\_irregular | String \(1500\) | Descriptive text entered by food business operator user to describe irregular opening days\. | Data entered by the food business operator user\. | Either opening\_days\_irregular has a value or the opening\_day\_monday through opening\_day\_sunday fields all have values\. | String\. | Irregular evenings when football match is held | N | Y | Y | Y | Y |
| Opening Day Monday | opening\_day\_monday | Boolean | Selected by food business operator user\. true if open this day, false if not\. | Data entered by the food business operator user\. | Either opening\_days\_irregular has a value or the opening\_day\_monday through opening\_day\_sunday fields all have values\. | When used, set within RAFB application to true or false\. | true, false | N | Y | Y | Y | Y |
| Opening Day Tuesday | opening\_day\_tuesday | Boolean | Selected by food business operator user\. true if open this day, false if not\. | Data entered by the food business operator user\. | When used, set within RAFB application to true or false\. | true, false | N | Y | Y | Y | Y |
| Opening Day Wednesday | opening\_day\_wednesday | Boolean | Selected by food business operator user\. true if open this day, false if not\. | Data entered by the food business operator user\. | When used, set within RAFB application to true or false\. | true, false | N | Y | Y | Y | Y |
| Opening Day Thursday | opening\_day\_thursday | Boolean | Selected by food business operator user\. true if open this day, false if not\. | Data entered by the food business operator user\. | When used, set within RAFB application to true or false\. | true, false | N | Y | Y | Y | Y |
| Opening Day Friday | opening\_day\_friday | Boolean | Selected by food business operator user\. true if open this day, false if not\. | Data entered by the food business operator user\. | When used, set within RAFB application to true or false\. | true, false | N | Y | Y | Y | Y |
| Opening Day Saturday | opening\_day\_saturday | Boolean | Selected by food business operator user\. true if open this day, false if not\. | Data entered by the food business operator user\. | When used, set within RAFB application to true or false\. | true, false | N | Y | Y | Y | Y |
| Opening Day Sunday | opening\_day\_sunday | Boolean | Selected by food business operator user\. true if open this day, false if not\. | Data entered by the food business operator user\. | When used, set within RAFB application to true or false\. | true, false | N | Y | Y | Y | Y |
| Opening Hours Monday | opening\_hours\_monday | String \(50\) | Free text description of the Monday opening hours of the food business establishment\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If opening\_hours\_monday is true then a value must be present\. | String\. | 09:00\-12:30 13:00\-18\+L55:L61:00 | N | Y | Y | Y | Y |
| Opening Hours Tuesday | opening\_hours\_tuesday | String \(50\) | Free text description of the Tuesday opening hours of the food business establishment\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If opening\_hours\_tuesday is true then a value must be present\. | String\. | 09:00\-12:30 13:00\-18:00 | N | Y | Y | Y | Y |
| Opening Hours Wednesday | opening\_hours\_wednesday | String \(50\) | Free text description of the Wednesday opening hours of the food business establishment\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If opening\_hours\_wednesday is true then a value must be present\. | String\. | 09:00\-12:30 | N | Y | Y | Y | Y |
| Opening Hours Thursday | opening\_hours\_thursday | String \(50\) | Free text description of the Thursday opening hours of the food business establishment\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If opening\_hours\_thursday is true then a value must be present\. | String\. | 09:00\-12:30 13:00\-18:00 | N | Y | Y | Y | Y |
| Opening Hours Friday | opening\_hours\_friday | String \(50\) | Free text description of the Friday opening hours of the food business establishment\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If opening\_hours\_friday is true then a value must be present\. | String\. | 09:00\-12:30 13:00\-18:00 | N | Y | Y | Y | Y |
| Opening Hours Saturday | opening\_hours\_saturday | String \(50\) | Free text description of the Saturday opening hours of the food business establishment\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If opening\_hours\_saturday is true then a value must be present\. | String\. | 10:00\-18:00 | N | Y | Y | Y | Y |
| Opening Hours Sunday | opening\_hours\_sunday | String \(50\) | Free text description of the Sunday opening hours of the food business establishment\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | If opening\_hours\_sunday is true then a value must be present\. | String\. | 10:30\-16:30 | N | Y | Y | Y | Y |
| Food Business Premises | premise | Data structure | This data structure conatins data on the food business premises | N | Y | Y | Y | Y |
| Establishment Address First Line | establishment\_first\_line | String \(256\) | First line \(or street number\) of the food business establishment address\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | 612 | N | Y | Y | Y | Y |
| Establishment Address Street | establishment\_street | String \(256\) | Street Name of the food business establishment address\. Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | Newport Road | N | Y | Y | Y | Y |
| Establishment Address Town | establishment\_town | String \(256\) | Town of the food business establishment address\. Data retrieved from the address record supplied by API call to the Postcoder service or entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | ASCII String\. | Cardiff | N | Y | Y | Y | Y |
| Establishment Address Postcode | establishment\_postcode | String \(8\) | Postcode of the food business establishment address\. Data entered by the food business operator user\. | Data entered by the food business operator user\. | Must be present\. | String npm validator isPostalCode \(GB\) | CF99 6TR | N | Y | Y | Y | Y |
| Establishment Address UPRN | establishment\_uprn | String \(12\) | UPRN \(Unique Property Reference Number\) of the food business establishment address\. Data retrieved from the address record supplied by API call to the Postcoder service\. | Data entered by the food business operator user\. | Highly desirable to be present\. May be missing in edge cases where address was not found in postcode lookup\. | Not applicable \- generated during postcode lookup\. | 824683234325 | N | Y | N | Y | Y |
| Establishment Type | establishment\_type | String \(50\) | Selected by the food business operator user from three options\. Place of business or commercial premises Mobile or moveable premises Home or domestic premises | Data entered by the food business operator user\. | Must be present\. | Not applicable \- selected via radio button in application\. | Mobile or moveable premises | N | Y | Y | Y | Y |
| Declaration | metadata | A data structure in the data set that contains the declaration data fields\. This structure is likely to be removed in a future release and the declaration data fields placed in the top\-level registrations structure\. | N | Y | Y | Y | Y |
| Declaration 1 | declaration1 | String | Food business operator user must tick agreement to this preset declaration\. | Food business operator user ticks box to confirm that they agree to this statement\. | Declaration text must be present in a food business registration record\. | User agreement captured in RAFB application\. | I declare that the information I have given on this form is correct and complete to the best of my knowledge and belief\. | Y | Y | Y | Y |
| Declaration 2 | declaration2 | String | Food business operator user must tick agreement to this preset declaration\. | Food business operator user ticks box to confirm that they agree to this statement\. | Declaration text must be present in a food business registration record\. | User agreement captured in RAFB application\. | The operator will notify their LA of any significant changes to the business activity, including closure, within 28 days of the change happening\. | Y | Y | Y | Y |
| Declaration 3 | declaration3 | String | Food business operator user must tick agreement to this preset declaration\. | Food business operator user ticks box to confirm that they agree to this statement\. | Declaration text must be present in a food business registration record\. | User agreement captured in RAFB application\. | The operator understands they are legally responsible for the safety and authenticity of the food being produced or served at this establishment\. | Y | Y | Y | Y |
