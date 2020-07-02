# Register A Food Business Data Standard

### What Is This Document?
This document describes the data standard for Register a Food Business service. It describes the fields, data types and structure, and contains guidance on acceptable values and which fields use specific reference data values.

It does this primarily from the viewpoint of a user recieving data from the service via the API.

This document does not include technical guidance for the service API. That information can be found in the [API documentation](https://github.com/fsadata/RegisterAFoodBusinessDataStandard/blob/master/Api%20Documentation.md).

### Who Is This Document For?
This document is aimed at the following users;

*   FSA users who want to understand the shape of the data collected by the service
*   Local Authorities who want to understand how to capture food business registration data in a consistent format

### What does the data look like?
The data will be supplied by the service as a nested JSON.

Please note the following fields are considered legacy fields which remain in the service for backwards compatibility with old integrations. These are;

*   `operator_first_line`
*   `operator_street`
*   `operator_dependent_locality`
*   `establishment_first_line`
*   `establishment_street`
*   `establishment_dependent_locality`

Example JSON
```
[{
  "id": 95,
  "fsa_rn": "ABCDEF-GHIJKL-MNOPQR",
  "council": "council-name",
  "competent_authority_id": "1234",
  "local_council_url": "https://www.example.com",
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
      "operator_dependent_locality": "Shotley Gate",
      "operator_address_line_1": "Flat 2",
      "operator_address_line_2": "612 Newport Road",
      "operator_address_line_3": "Shotley Gate",
      "operator_town": "generic-town",
      "operator_primary_number": "01234567891",
      "operator_secondary_number": "01234567891",
      "operator_email": "generic@email.com",
      "contact_representative_name": "joe blogs",
      "contact_representative_role": "restaurant manager",
      "contact_representative_number": "01234567891",
      "contact_representative_email": "generic@email.com",
      "partners": [["john smith", true], ["julian wills", false]]
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
      "establishment_dependent_locality": "Shotley Gate",
      "establishment_address_line_1": "42 Wallaby Way",
      "establishment_address_line_2": "Sydney",
      "establishment_address_line_3": "Australia"
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

---

Full field information can be found for each field below, but a short summary table of the most basic attributes is included here for reference.

## Quick Reference

| No. | Field name | JSON name | Data type and size | Description |
|-----|------------|-----------|--------------------|-------------|
| 01 | Food Business Registration | `registration` | Data structure | The top-level data structure for a single registration. |
| 02 | Food Business Reference Number | `fsa_rn` | String (20) | Food Standards Agency transaction Reference Number. |
| 03 | Local Authority | `council` | String \(50\) | The name of the local authority (or competent authority) that the service associates with the registration. |
| 04 | Competent Authority ID | `competent_authority_id` | String (4) | Competent authority identifier, this is configuration data that originates from the register of competent authorities. |
| 05 | Local Council URL | `local_council_url` | String (50) | Local Authority URL, this is configuration data identifying the URL name for the local authority. |
| 06 | Record Collected | `collected` | Boolean | True if registration has been collected, false if not. |
| 07 | Record Collection Date | `collected_at` | ISO date time | Date and time the registration was collected. |
| 08 | Record Creation Date | `createdAt` | ISO date time | The date and time the reigstration record was created. |
| 09 | Record Updated Date | `updatedAt` | ISO date time | The date and time of most recent update to the registration record. |
| 10 | Food Business Establishment | `establishment` | Data structure |||| This data structure contains the establishment details, operator, premises and business activity information within the registration\. ||| Y | N | Y | Y |
| 11 | Establishment Trading Name | `establishment_trading_name` | String (50) | Proposed trading name of the new food business. |
| 12 | Establishment Opening Date | `establishment_opening_date` | ISO8061 date | Opening date of the food business. |
| 13 | Establishment Primary Telephone Number | `establishment_primary_number` | String (15) | Primary telephone number of the food business. |
| 14 | Establishment Secondary Telephone Number | `establishment_secondary_number` | String (15) | Secondary telephone number of the food business. |
| 15 | Establishment Email Address | `establishment_email` | String (254) | Email address of the food business establishment. |
| 16 | Food Business Operator | `operator` | Data structure | This data structure contains the operator details. |
| 17 | Establishment Operator Type | `operator_type` | String | Type of food business operator; sole trader, partnership, limited company, person, or charity. |
| 18 | Operator Company Name | `operator_company_name` | String (50) | The name of the operating company, where the "limited company" operator type has been selected. |
| 19 | Operator Companies House Reference Number | `operator_company_house_number` | String (8) | The Companies House reference number, where the "limited company" operator type has been selected. |
| 20 | Operator Charity Name | `operator_charity_name` | String (50) | The name of the operating charity, where the "charity" operator type has been selected. |
| 21 | Operator Charity Number | `operator_charity_number` | String (8) | The charity reference number, where the "chairty" operator type has been selected. |
| 22 | Operator First Name | `operator_first_name` | String (70) | The first name of the operator, where the "sole trader" operator type has been selected. |
| 23 | Operator Last Name | `operator_last_name` | String (70) | The last name of the operator, where the "sole trader" operator type has been selected. |
| 24 | Operator Postcode | `operator_postcode` | String (8) | Postcode of the operator address. |
| 25 | Operator Address First Line | `operator_first_line` | String (70) | First line (or street number) of operator address. |
| 26 | Operator Address Street | `operator_dependent_locality` | String (256) | Locality of the food business operator address. |
| 27 | Operator Address Locality | `operator_street` | String (256) | The locality is an optional field that will be present in some addresses. Locality can help differentiate a small town, village or other area from a larger town or city nearby that populates the town field for that address. |
| 28 | Operator Address Label Line 1 | `operator_address_line_1` | String (256) | Alternative presentation of the address that combines required PAF fields into an address label. |
| 29 | Operator Address Label Line 2 | `operator_address_line_2` | String (256) | Alternative presentation of the address that combines required PAF fields into an address label. |
| 30 | Operator Address Label Line 3 | `operator_address_line_3` | String (256) | Alternative presentation of the address that combines required PAF fields into an address label. |
| 31 | Operator Address Town | `operator_town` | String (256) | Town of operator address. Data retrieved from the address record supplied by API call to the Postcoder service or entered by the user. |
| 32 | Operator Address UPRN | `operator_uprn` | String (12) | Unique Property Reference Number of the operator address. |
| 33 | Operator Primary Telephone Number | `operator_primary_number` | String (15) | Operator primary telephone number. |
| 34 | Operator Secondary Telephone Number | `operator_secondary_number` | String (15) | Operator secondary telephone number. |
| 35 | Operator Email Address | `operator_email` | String (254) | Email address of the food business operator. |
| 36 | Operator Contact Representative | `contact_representative_name` | String (70) | Name of person representing the food business operator. |
| 37 | Operator Contact Role | `contact_representative_role` | String (256) | Role of the person representing the food business operator. |
| 38 | Operator Contact Phone Number | `contact_representative_number` | String (15) | Phone number for the person representing the food business operator. |
| 39 | Operator Contact Email Address | `contact_representative_email` | String (254) | Email address for the person representing the food business operator. |
| 40 | Operator Partners | `partners` | String array | Array of partner data – containing sets of between two and five `partner_name` and `partner_is_primary_contact` data fields, limited to the first five partners. |
| 41 | Operator Partner Name | `partner_name` | String (56) | Partner name as entered by the food business operator user. |
| 42 | Operator Partner Primary Contact | `partner_is_primary_contact` | Boolean | A value of `true` means the partner is the primary contact for this registration, and `false` means the partner is not the primary contact. |
| 43 | Food Business Activities | `activities` | Data structure | This data structure describes the activities of the food business |
| 44 | Customer Type | `customer_type` | String | The type of customers served by the food business. Must be one of the following three values: `End consumer`, `Other businesses`, `End consumer and other businesses`. |
| 45 | Business Type | `business_type` | String | Type of food business as selected by the user from a predefined list. |
| 46 | Business Type Search Term | `business_type_search_term` | String | Search term used by the food business operator user to find a business type. |
| 47 | Import Export Activities | `import_export_activities` | String | The user selects the type of import and export activity from four choice:. `None`, `Directly import`, `Directly export`, `Directly import and export`. |
| 48 | Water Supply | `water_supply` | String | Selected by the user from the following values: `Public`, `Private`, `Private and public`. |
| 49 | Business Other Details | `business_other_details` | String (150) | Additional information that the food business operator user may enter to accurately describe what the business does. |
| 50 | Opening Days Irregular | `opening_days_irregular` | String (1500) | Descriptive text entered by food business operator user to describe irregular opening days. |
| 51 | Opening Day Monday | `opening_day_monday` | Boolean | Value is `true` if open Mondays, `false` if not. |
| 52 | Opening Day Tuesday | `opening_day_tuesday` | Boolean | Value is `true` if open Tuesdays, `false` if not. |
| 53 | Opening Day Wednesday | `opening_day_wednesday` | Boolean | Value is `true` if open Wednesdays, `false` if not. |
| 54 | Opening Day Thursday | `opening_day_thursday` | Boolean | Value is `true` if open Thursdays, `false` if not. |
| 55 | Opening Day Friday | `opening_day_friday` | Boolean | Value is `true` if open Fridays, `false` if not. |
| 56 | Opening Day Saturday | `opening_day_saturday` | Boolean | Value is `true` if open Saturdays, `false` if not. |
| 57 | Opening Day Sunday | `opening_day_sunday` | Boolean | Value is `true` if open Sundays, `false` if not. |
| 58 | Opening Hours Monday | `opening_hours_monday` | String (50) | Free text description of the Monday opening hours. |
| 59 | Opening Hours Tuesday | `opening_hours_tuesday` | String \(50\) | Free text description of the Tuesday opening hours. |
| 60 | Opening Hours Wednesday | `opening_hours_wednesday` | String (50) | Free text description of the Wednesday opening hours. |
| 61 | Opening Hours Thursday | `opening_hours_thursday` | String (50) | Free text description of the Thursday opening hours. |
| 62 | Opening Hours Friday | `opening_hours_friday` | String (50) | Free text description of the Friday opening hours. |
| 63 | Opening Hours Saturday | `opening_hours_saturday` | String (50) | Free text description of the Saturday opening hours. |
| 64 | Opening Hours Sunday | `opening_hours_sunday` | String (50) | Free text description of the Sunday opening hours. |
| 65 | Food Business Premises | `premise` | Data structure | This data structure conatins data on the food business premises. |
| 66 | Establishment Address First Line | `establishment_first_line` | String (256) | First line (or street number) of the establishment address. **This is a legacy field which remains solely to support older integrations.** |
| 67 | Establishment Address Street | `establishment_street` | String (256) | Street name of the establishment address. |
| 68 | Establishment Address Locality | `establishment_dependent_locality` | String (256) | The locality is an optional field that will be present in some addresses. Locality can help differentiate a small town, village, or other area from a larger town or city nearby that populates the town field for that address. |
| 69 | Establishment Address Label Line 1 | `establishment_address_line_1` | String (256) | Establishment Address Label Line 1. Alternative presentation of the address that combines required PAF fields into an address label. |
| 70 | Establishment Address Label Line 2 | `establishment_address_line_2` | String (256) | Establishment Address Label Line 2. Alternative presentation of the address that combines required PAF fields into an address label. |
| 71 | Establishment Address Label Line 3 | `establishment_address_line_3` | String (256) | Establishment Address Label Line 3. Alternative presentation of the address that combines required PAF fields into an address label. |
| 72 | Establishment Address Town | `establishment_town` | String (256) | Town of the establishment address. |
| 73 | Establishment Address Postcode | `establishment_postcode` | String (8) | Postcode of the establishment address. |
| 74 | Establishment Address UPRN | `establishment_uprn` | String (12) | The Unique Property Reference Number of the establishment address. |
| 75 | Establishment Type | `establishment_type` | String (50) | Selected by the user from three options: `Place of business or commercial premises`, `Mobile or moveable premises`, `Home or domestic premises`. |
| 76 | Declaration | `metadata` | Data structure | This structure is likely to be removed in a future release and the declaration data fields placed in the top-level registrations structure. |
| 77 | Declaration 1 | `declaration1` | String | The user must tick "agree" to this preset declaration. |
| 78 | Declaration 2 | `declaration2` | String | The user must tick "agree" to this preset declaration. |
| 79 | Declaration 3 | `declaration3` | String | The user must tick "agree" to this preset declaration. |

## Field Definitions
1.  [Food Business Registration](#1-food-business-registration)
2.  [Food Business Reference Number](2-#food-business-reference-number)
3.  [Local Authority](#3-local-authority)
4.  [Competent Authority ID](#4-competent-authority-id)
5.  [Local Council URL](#5-local-council-url)
6.  [Record Collected By LA](#6-record-collected-by-la)
7.  [Record Collected By LA At](#7-record-collected-by-la-at)
8.  [Record Created At](#8-record-created-at)
9.  [Record Updated At](#9-record-updated-at)
10. [Food Business Establishment](#10-food-business-establishment)
11. [Establishment Trading Name](#11-establishment-trading-name)
12. [Establishment Opening Date](#12-establishment-opening-date)
13. [Establishment Primary Telephone Number](#13-establishment-primary-telephone-number)
14. [Establishment Secondary Telephone Number](#14-establishment-secondary-telephone-number)
15. [Establishment Email Address](#15-establishment-email-address)
16. [Food Business Operator](#16-food-business-operator)
17. [Establishment Operator Type](#17-establishment-operator-type)
18. [Operator Company Name](#18-operator-company-name)
19. [Operator Companies House Reference Number](#19-operator-companies-house-reference-number)
20. [Operator Charity Name](#20-operator-charity-name)
21. [Operator Charity Number](#21-operator-charity-number)
22. [Operator First Name](#22-operator-first-name)
23. [Operator Last Name](#23-operator-last-name)
24. [Operator Postcode](#24-operator-postocde)
25. [Operator Address First Line](#25-operator-address-first-line)
26. [Operator Address Street](#26-operator-address-street)
27. [Operator Address Locality](#27-operator-address-locality)
28. [Operator Address Label Line 1](#28-operator-address-line-label-1)
29. [Operator Address Label Line 2](#29-operator-address-line-label-2)
30. [Operator Address Label Line 3](#30-operator-address-line-label-3)
31. [Operator Address Town](#31-operator-address-town)
32. [Operator Address UPRN](#32-operator-address-uprn)
33. [Operator Primary Telephone Number](#33-operator-primary-telephone-number)
34. [Operator Secondary Telephone Number](#34-operator-secondary-telephone-number)
35. [Operator Email Address](#35-operator-email-address)
36. [Operator Contact Representative](#36-operatpr-contact-representative)
37. [Operator Contact Role](#37-operator-contact-role)
38. [Operator Contact Phone Number](#38-operator-contact-phone-number)
39. [Operator Contact Email Address](#39-operator-contact-email-address)
40. [Operator Partners](#40-operator-partners)
41. [Operator Partner Name](#41-operator-partner-name)
42. [Operator Partner Is primary Contact](#42-operator-partner-is-primary-contact)
43. [Food Business Activities](#43-food-business-activities)
44. [Customer Type](#44-customer-type)
45. [Business Type](#45-business-type)
46. [Business Type Search Term](#46-business-type-search-term)
47. [Import Export Activities](#47-import-export-activities)
48. [Water Supply](#48-water-supply)
49. [Business Other Details](#49-business-other-details)
50. [Opening Days Irregular](#50-opening-days-irregular)
51. [Opening Day Monday](#51-opening-day-monday)
52. [Opening Day Tuesday](#52-opening-day-tuesday)
53. [Opening Day Wednesday](#53-opening-day-wednesday)
54. [Opening Day Thursday](#54-opening-day-thursday)
55. [Opening Day Friday](#55-opening-day-friday)
56. [Opening Day Saturday](#56-opening-day-saturday)
57. [Opening Day Sunday](#57-opening-day-sunday)
58. [Opening Hours Monday](#58-opening-hours-monday)
59. [Opening Hours Tuesday](#59-opening-hours-tuesday)
60. [Opening Hours Wednesday](#60-opening-hours-wednesday)
61. [Opening Hours Thursday](#61-opening-hours-thursday)
62. [Opening Hours Friday](#62-opening-hours-friday)
63. [Opening Hours Saturday](#63-opening-hours-saturday)
64. [Opening Hours Sunday](#64-opening-hours-sunday)
65. [Food Business Premises](#65-food-business-premises)
66. [Establishment Address First Line](#66-estabishment-address-first-line)
67. [Establishment Address Street](#67-establishment-address-street)
68. [Establishment Address Locality](#68-establishment-address-locality)
69. [Establishment Address Label Line 1](#69-establishment-address-line-1)
70. [Establishment Address Label Line 2](#70-establishment-address-line-2)
71. [Establishment Address Label Line 3](#71-establishment-address-line-3)
72. [Establishment Address Town](#72-establishment-address-town)
73. [Establishment Address Postcode](#73-estabishment-address-postcode)
74. [Establishment Address UPRN](#74-estabishment-address-uprb)
75. [Establishment Type](#75-estabishment-type)
76. [Declaration](#76-declaration)
77. [Declaration 1](#77-declaration-1)
78. [Declaration 2](#78-declaration-2)
79. [Declaration 3](#79-declaration-3)  

## Details  

### 1. Food Business Registration
**Field name:** `registration`  
**Data type and size:** Data structure  
**Description:** The top-level data structure for a single registration  
**Source:**  
**Validation rules:**  
**Validation implementation:**  
**Example:**  
**Personal data:** Yes.  
**Data sent in notification emails:** No.  

### 2. Food Business Registration Reference Number
**Field name:** `fsa_rn`  
**Data type and size:** String (20)  
**Description:** A unique identifier generated for each food business registration.  
**Source:** Generated by calling the FSA-RN micorservice at `https://fsa-reference-numbers.epimorphics.net/generate/{councilCode}/{typeCode}` where the `councilCode` represents the local authority code in the [FSA register of competent authorities](https://data.food.gov.uk/codes/reference-number/_authority). `TypeCode` is `001` for production or `000` for the development and test service.  
**Validation rules:** Must be present in a food business registration record.  
**Validation implementation:** Not applicable, geenrated by the service.  
**Example:** `"AHFGHL-CNFVJQ-D6H8BH"`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 3. Local Authority
**Field name:** `council`  
**Data type and size:** String (50)  
**Description:** The name of the Local Authority that the service associates with the registration.  
**Source:** Generated as configuration data within the registration service.  
**Validation rules:** Must be present in a food business registration record.  
**Validation implementation:** Must be present in a food business registration record.  
**Example:** `"Vale of Glamorgan Council"`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 4. Competent Authority ID
**Field name:** `competent_authority_id`  
**Data type and size:** String (4)  
**Description:** Competent authority identifier.  This is configuration data that originates from the [register of competent authorities](https://data.food.gov.uk/codes/reference-number/_authority) which includes Local Authorities and Port Health Authorities.  
**Source:** Generated as configuration data within the registration service.  
**Validation rules:** Must be present in a food business registration record.  
**Validation implementation:** Must be present in a food business registration record.  
**Example:** `"0000"`  
**Personal data:** No.  
**Data sent in notification emails:** No.  

### 5. Local Council URL
**Field name:** `local_council_url`  
**Data type and size:** String (50)  
**Description:** Local Authority URL.  This is configuration data identifying the URL name for the local authority.  
**Source:** Generated as configuration data within the registration service.  
**Validation rules:** Must be present in a food business registration record.  
**Validation implementation:** Must be present in a food business registration record.  
**Example:** "<https://www.example.com>"  
**Personal data:**  No  
**Data sent in notification emails:** No.  

### 6. Record Collected By LA
**Field name:** `collected`  
**Data type and size:** Boolean  
**Description:** `True` if registration has been collected and `false` if registration has not been collected.  
**Source:** Set via PUT method in the RAFB collections API called by external service.  
**Validation rules:** The default value is `false` and can be set to true or false.  
**Validation implementation:** Can only be set to `true` or `false`.  
**Example:** `true` `false`  
**Personal data:** No  
**Data sent in notification emails:** No.  


### 7. Record Collected By LA At
**Field name:** `collected_at`  
**Data type and size:** ISO date time  
**Description:** The date and time of collection of the registration.  
**Source:** Generated within the registration service.  
**Validation rules:** Will contain a value if the collected flag has been set (or reset).  
**Validation implementation:** Must be a date time value.  
**Example:** `2019-04-16T13:15:06.022Z`  
**Personal data:** No.  
**Data sent in notification emails:** No.  

### 8. Record Created At
**Field name:** `createdAt`  
**Data type and size:** ISO date time  
**Description:** Date time the registration record was created.  
**Source:** Generated within the registration .  
**Validation rules:** Must be set.  
**Validation implementation:** Set by the service.  
**Example:** `2019-04-16T13:15:06.022Z`  
**Personal data:** No.  
**Data sent in notification emails:** No.  

### 9. Record Updated At
**Field name:** `updatedAt`  
**Data type and size:** ISO date time  
**Description:** The date and time most recent update of record.  
**Source:** Generated within the registration service.  
**Validation rules:** Will only be set if record has been updated after creation.  
**Validation implementation:** Set by the service.  
**Example:** `2019-04-16T13:15:06.022Z`  
**Personal data:** No.  
**Data sent in notification emails:** No.  

### 10. Food Business Establishment
**Field name:** `establishment`  
**Data type and size:** Data structure  
**Description:** This data structure contains the establishment details, operator, premises and business activity information within the registration.  
**Source:**  N/A.
**Validation rules:**  N/A.  
**Validation implementation:**  N/A.  
**Example:**  N/A.  
**Personal data:** N/A.  
**Data sent in notification emails:** No.   

### 11. Establishment Trading Name
**Field name:** `establishment_trading_name`  
**Data type and size:** String (50)  
**Description:** The proposed trading name of the new food business. Collection allows comparison of RAFB and FHRS data.  
**Source:** Data entered by the user.  
**Validation rules:** Must be provided in this data set.  
**Validation implementation:** ASCII string  
**Example:** `"Tropical Pizzas"`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 12. Establishment Opening Date
**Field name:** `establishment_opening_date`  
**Data type and size:** ISO8061 date  
**Description:** Opening date of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** Opening date or estimated opening date must be provided.  
**Validation implementation:** Date String is ISO8601.  
**Example:** `2017-12-29`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 13. Establishment Primary Telephone Number
**Field name:** `establishment_primary_number`  
**Data type and size:** String (15)  
**Description:** Primary telephone number of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** Valid phone number must be provided.  
**Validation implementation:** Numeric string between 5 and 20 characters (5 < x < 20). Allows ``""blank space""`` and `+`.  
**Example:** `02921455657` or `029 21455657`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 14. Establishment Secondary Telephone Number
**Field name:** `establishment_secondary_number`  
**Data type and size:** String (15)  
**Description:** Secondary telephone number of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** Optional, must be a valid phone number if provided.  
**Validation implementation:** Numeric string between 5 and 20 characters (5 < x < 20). Allows `""blank space""` and `+`.  
**Example:** `07976765432` or `+4435021022345`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 15. Establishment Email Address
**Field name:** `establishment_email`  
**Data type and size:** String (254)  
**Description:** Email address of the food business establishment.  
**Source:** Data entered by the user.  
**Validation rules:** Valid email address must be provided.  
**Validation implementation:** "String, npm validator isEmail"  
**Example:** orders@tropical-pizzas.co.uk  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 16. Food Business Operator
**Field name:** `operator`  
**Data type and size:** Data structure  
**Description:** This data structure contains the operator type and details. The operator address can be processed in one of two ways.
1. Use the operator_uprn to match the address to your own address gazetteer records.
2. Construct the address using the address label fields:  `operator_address_line_1`, `operator_address_line_2`, `operator_address_line_3`, `operator_town`, `operator_postcode`.
**Source:** N/A.  
**Validation rules:** N/A.  
**Validation implementation:** N/A.  
**Example:** N/A.  
**Personal data:** N/A.
**Data sent in notification emails:** No.  

### 17. Establishment Operator Type
**Field name:** `operator_type`  
**Data type and size:** String  
**Description:** Defines the type of food business operator. The answer to this question determines the data captured about the operator of the establishment.  
**Source:** Data entered by the user.  
**Validation rules:** One of five fixed values. `Sole trader`, `Partnership`, `A company (registered by a representative)` for limited companies, `A person (registered by a representative)` for persons registered by a representative, or `A charity (registered by a representative)` for charities.  
**Validation implementation:** Radio button selection in service.  
**Example:** `Sole trader`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 18. Operator Company Name
**Field name:** `operator_company_name`  
**Data type and size:** String (50)  
**Description:** For limited companies only, the operating company name.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present when operator type is limited company.  
**Validation implementation:** String.  
**Example:** Tropical Pizzas South Wales Limited  
**Personal data:** Yes.
**Data sent in notification emails:** Yes.  

### 19. Operator Companies House Reference Number
**Field name:** `operator_company_house_number`  
**Data type and size:** String (8)  
**Description:** For limited companies only, the operating company reference number from Companies House.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present when operator type is limited company.  
**Validation implementation:** String, 8 characters in length, first two characters numeric.  
**Example:** `12345678`  
**Personal data:** Yes.
**Data sent in notification emails:** Yes.  

### 20. Operator Charity Name
**Field name:** `operator_charity_name`  
**Data type and size:** String (50)  
**Description:** For charities only, the operating charity name.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present when operator type is charity.  
**Validation implementation:** String.  
**Example:** `Fred Wills Trust`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 21. Operator Charity Number
**Field name:** `operator_charity_number`  
**Data type and size:** String (8)  
**Description:** For charities only, the chairty registration number.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present when operator type is charity.  
**Validation implementation:** String, allows `-`, between 6 and 8 characters in length.  
**Example:** `10028465`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 22. Operator First Name
**Field name:** `operator_first_name`  
**Data type and size:** String (70)  
**Description:** For sole traders and persons only, the first name of the sole trader or person.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present when operator type is person or sole trader.  
**Validation implementation:** String.  
**Example:** `Julian`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 23. Operator Last Name
**Field name:** `operator_last_name`  
**Data type and size:** String (70)  
**Description:** For sole traders and persons only, the last name of the sole trader or person.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present when operator type is person or sole trader.  
**Validation implementation:** String.  
**Example:** `Wills`  
**Personal data:** Yes.
**Data sent in notification emails:** Yes.  

### 24. Operator Postcode
**Field name:** `operator_postcode`  
**Data type and size:** String (8)  
**Description:** Postcode of the operator address.  
**Source:** Data entered by user.  
**Validation rules:** Must be present.  
**Validation implementation:** String, passes npm validator `isPostalCode (GB)`  
**Example:** `CF23 5AT`  
**Personal data:** Yes.
**Data sent in notification emails:** Yes.    

### 25. Operator Address First Line
**Field name:** `operator_first_line`  
**Data type and size:** String (70)  
**Description:** This is a legacy field, it is still presented within the data standard for legacy integrations. This field may be removed from the standard at a later date and should not be used for new integrations. This field is a mirror of `operator_address_line_1`.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `241`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 26. Operator Address Street
**Field name:** `operator_street`  
**Data type and size:** String (256)  
**Description:** This is a legacy field, it is still presented within the data standard for legacy integrations. This field may be removed from the standard at a later date and should not be used for new integrations. This field is a mirror of `operator_address_line_2`.  
**Source:** Data entered by the food business operator user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `Southminster Road`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 27. Operator Address Locality
**Field name:** `operator_dependent_locality`  
**Data type and size:** String (256)  
**Description:** This is a legacy field, it is still presented within the data standard for legacy integrations. This field may be removed from the standard at a later date and should not be used for new integrations. This field is a mirror of `operator_address_line_3`.  
**Source:** Data entered or confirmed by the user.  
**Validation rules:** Optional.  
**Validation implementation:** ASCII String.  
**Example:** `Shotley Gate`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 28. Operator Address Label Line 1
**Field name:** `operator_address_line_1`  
**Data type and size:** String (256)  
**Description:** An alternative presentation of the address that combines required PAF fields into an address label.  
**Source:** Data returned by postcode lookup service.
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `Flat 2`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 29. Operator Address Label Line 2
**Field name:** `operator_address_line_2`  
**Data type and size:** String (256)  
**Description:** An alternative presentation of the address that combines required PAF fields into an address label.  
**Source:** Data returned by postcode lookup.
**Validation rules:** May be present.
**Validation implementation:** ASCII String.  
**Example:** `612 Newport Road`
**Personal data:**  Yes.
**Data sent in notification emails:** Yes.  

### 30. Operator Address Label Line 3
**Field name:** `operator_address_line_3`  
**Data type and size:** String (256)  
**Description:** An alternative presentation of the address that combines required PAF fields into an address label.  
**Source:** Data returned by postcode lookup.  
**Validation rules:** May be present.
**Validation implementation:** ASCII String.  
**Example:** `Shotley Gate`  
**Personal data:**  Yes.
**Data sent in notification emails:** Yes.  

### 31. Operator Address Town
**Field name:** `operator_town`  
**Data type and size:** String (256)  
**Description:** The town of the operator's address.  
**Source:** Data entered by the food business operator user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `Cardiff`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 32. Operator Address UPRN
**Field name:** `operator_uprn`  
**Data type and size:** String (12)  
**Description:** The Unique Property Reference Number of the operator's address.  
**Source:** Data generated from the postcode lookup and validation API calls.  
**Validation rules:** Optional, but desirable. May be missing in edge cases where address was not found in postcode lookup.  
**Validation implementation:** N/A.  
**Example:** `520887636906`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 33. Operator Primary Telephone Number
**Field name:** `operator_primary_number`  
**Data type and size:** String (15)  
**Description:** Operator primary telephone number.  
**Source:** Data entered by the user.  
**Validation rules:** A string of permitted characters.  
**Validation implementation:** String, between 5 and 20 characters, allows blank spaces and `+`  
**Example:** `02921455657` or `+4429 21455657`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 34. Operator Secondary Telephone Number
**Field name:** `operator_secondary_number`  
**Data type and size:** String (15)  
**Description:** Operator secondary telephone number.  
**Source:** Data entered by the user.  
**Validation rules:** Optional, must be a string of permitted characters.  
**Validation implementation:** String, between 5 and 20 characters, allows blank spaces and `+`  
**Example:** `07976765432` or `+4435021022345`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 35. Operator Email Address
**Field name:** `operator_email`  
**Data type and size:** String (254)  
**Description:** Email address of the food business operator.  
**Source:** Data entered by the user.  
**Validation rules:** Valid email address must be provided.  
**Validation implementation:** "String,
npm validator isEmail"  
**Example:** orders@tropical-pizzas.co.uk  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 36. Operator Contact Representative
**Field name:** `contact_representative_name`  
**Data type and size:** String (70)  
**Description:** The name of the person representing the food business operator.  
**Source:** Data entered by the user.  
**Validation rules:** If business type is `Limited Company` or `Charity` then a value must be present.  
**Validation implementation:** ASCII String.  
**Example:** `John Smith`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 37. Operator Contact Role
**Field name:** `contact_representative_role`  
**Data type and size:** String (256)  
**Description:** The role of the person representing the food business operator.  
**Source:** Data entered by the user.  
**Validation rules:** If business type is `Limited Company` or `Charity` then a value must be present.  
**Validation implementation:** ASCII String.  
**Example:** `Restaurant Manager`  
**Personal data:** Yes.
**Data sent in notification emails:** Yes.  

### 38. Operator Contact Phone Number
**Field name:** `contact_representative_number`  
**Data type and size:** String (15)  
**Description:** The contact phone number for the person representing the food business operator.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `7976765432`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 39. Operator Contact Email Address
**Field name:** `contact_representative_email`  
**Data type and size:** String (254)  
**Description:** The email address for the person representing the food business operator.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `julian@tropical-pizzas.co.uk`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 40. Operator Partners
**Field name:** `partners`  
**Data type and size:** String array  
**Description:** An array of partner data, between two and five `partner_name` and `partner_is_primary_contact` data fields. Currently limited to the first five partners (noting that some partnerships have more than this).  One `partner_is_primary_contact` field will have a value of `true` and the others will have a value of `false`.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present when operator type is `partnership`.  
**Validation implementation:** The array must contain between 2 and 5 partners. One partner must be the primary contact.  
**Example:** `["john smith", true], ["julian wills", false]`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 41. Operator Partner Name
**Field name:** `partner_name`  
**Data type and size:** String (56)  
**Description:** Partner name.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present for a partnership.  
**Validation implementation:** String.  
**Example:** `Joan Smith`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 42. Operator Partner Is primary Contact
**Field name:** `partner_is_primary_contact`  
**Data type and size:** Boolean  
**Description:** A value of `true` means the partner is the primary contact for this registration, and `false` means the partner is not the primary contact.  
**Source:** Data entered by the user as a choice against each partner entered.  
**Validation rules:** Must be set for each partner in the partner array.  One partner must be set to true and all others present must be false.  
**Validation implementation:** N/A. Set by user choice of radio button in the RAFB .  
**Example:** `true` or `false`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 43. Food Business Activities
**Field name:** `activities`  
**Data type and size:** Data structure  
**Description:** This data structure describes the activities of the food business.  
**Source:** N/A.  
**Validation rules:** N/A.  
**Validation implementation:** N/A.  
**Example:** N/A.  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 44. Customer Type
**Field name:** `customer_type`  
**Data type and size:** String  
**Description:** A value selected by the user for the type of customers served by the food business.  
**Source:** Data entered by the user.  
**Validation rules:** Must be one of the following three values: `End consumer`, `Other businesses`, or `End consumer and other businesses.`  
**Validation implementation:** One of the values in the customer type list must be selected.  
**Example:** `End consumer`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 45. Business Type
**Field name:** `business_type`  
**Data type and size:** String  
**Description:** A value to describe the type of food business being registered selected by the user from a predefined list.  
**Source:** Data selection made by the user from a predefined list.  
**Validation rules:** Must be present and must be validated against the list of [business types](https://github.com/FoodStandardsAgency/register-a-food-business-front-end/blob/master/src/components/business-type-transformed.json), which is loaded  as the displayName field.  
**Validation implementation:** One of the values in the business type list must be selected.  
**Example:** `Livestock farm`, `Greengrocer`, `Shellfish purification centre`, `Commercial bakery`, `Alcoholic drinks manufacturer`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 46. Business Type Search Term
**Field name:** `business_type_search_term`  
**Data type and size:** String  
**Description:** The search term used by the food business operator user to find a business type. This is a predefined list that maps `business_type_search_term` values to a specific business type. Field mapping is stored in [this file](https://github.com/FoodStandardsAgency/register-a-food-business-front-end/blob/master/src/components/business-type-transformed.json).  
**Source:** Data entered by the user.  
**Validation rules:** Optional part of the data set used to help identify a business type.  
**Validation implementation:** One of the values in the business type Search Term list must be selected.  
**Example:** `Pig`, `Bee`, `Halal`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 47. Import Export Activities
**Field name:** `import_export_activities`  
**Data type and size:** String  
**Description:** The user selects the type of import and export activity from four choices: `None`, `Directly import`, `Directly export`, `Directly import and export`.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present  
**Validation implementation:** N/A. Radio button selection in .  
**Example:** `Directly import and export`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 48. Water Supply
**Field name:** `water_supply`  
**Data type and size:** String  
**Description:** Selected by the user from one of the following values: `Public`, `Private`, `Private and public`.  
**Source:** Data entered by the user.  
**Validation rules:** Must be one of the following values: `Public`, `Private`, `Private and public`.  
**Validation implementation:** N/A. User choice captured by RAFB .  
**Example:** `Private` `Private and public`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 49. Business Other Details
**Field name:** `business_other_details`  
**Data type and size:** String (150)  
**Description:** Additional information that the user may enter to accurately describe what the business does.  
**Source:** Data entered by the user.  
**Validation rules:** Optional information.  
**Validation implementation:** String.  
**Example:** `Shop making artisan chocolates in Greenwich.`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 50. Opening Days Irregular
**Field name:** `opening_days_irregular`  
**Data type and size:** String (1500)  
**Description:** Descriptive text entered by food business operator user to describe irregular opening days.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through to `opening_day_sunday` fields all have values.  
**Validation implementation:** String.  
**Example:** `Irregular evenings when football match is held.`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 51. Opening Day Monday
**Field name:** `opening_day_monday`  
**Data type and size:** Boolean  
**Description:** Selected by food business operator user. The value is `true` if open on Mondays, `false` if not.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through `opening_day_sunday` fields all have values.  
**Validation implementation:** When used, set within RAFB  to `true` or `false`.  
**Example:** `true`, `false`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 52. Opening Day Tuesday
**Field name:** `opening_day_tuesday`  
**Data type and size:** Boolean  
**Description:** Selected by food business operator user. The value is `true` if open on Tuesdays, `false` if not.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through `opening_day_sunday` fields all have values.  
**Validation implementation:** When used, set within RAFB  to `true` or `false`.  
**Example:** `true`, `false`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 53. Opening Day Wednesday
**Field name:** `opening_day_wednesday`  
**Data type and size:** Boolean  
**Description:** Selected by food business operator user. The value is `true` if open on Wednesdays, `false` if not.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through `opening_day_sunday` fields all have values.  
**Validation implementation:** When used, set within RAFB  to `true` or `false`.  
**Example:** `true`, `false`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 54. Opening Day Thursday
**Field name:** `opening_day_thursday`  
**Data type and size:** Boolean  
**Description:** Selected by food business operator user. The value is `true` if open on Thursdays, `false` if not.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through `opening_day_sunday` fields all have values.  
**Validation implementation:** When used, set within RAFB  to `true` or `false`.  
**Example:** `true`, `false`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 55. Opening Day Friday
**Field name:** `opening_day_friday`  
**Data type and size:** Boolean  
**Description:** Selected by food business operator user. The value is `true` if open on Fridays, `false` if not.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through `opening_day_sunday` fields all have values.  
**Validation implementation:** When used, set within RAFB  to `true` or `false`.  
**Example:** `true`, `false`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 56. Opening Day Saturday
**Field name:** `opening_day_saturday`  
**Data type and size:** Boolean  
**Description:** Selected by food business operator user. The value is `true` if open on Saturdays, `false` if not.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through `opening_day_sunday` fields all have values.  
**Validation implementation:** When used, set within RAFB  to `true` or `false`.  
**Example:** `true`, `false`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 57. Opening Day Sunday
**Field name:** `opening_day_sunday`  
**Data type and size:** Boolean  
**Description:** Selected by food business operator user. The value is `true` if open on Sundays, `false` if not.  
**Source:** Data entered by the user.  
**Validation rules:** Either `opening_days_irregular` has a value or the `opening_day_monday` through `opening_day_sunday` fields all have values.  
**Validation implementation:** When used, set within RAFB  to `true` or `false`.  
**Example:** `true`, `false`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 58. Opening Hours Monday
**Field name:** `opening_hours_monday`  
**Data type and size:** String (50)  
**Description:** A free text description of the Monday opening hours of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** If `opening_hours_monday` is true then a value must be present.  
**Validation implementation:** String.  
**Example:** `09:00-12:30`, `13:00-18:00`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 59. Opening Hours Tuesday
**Field name:** `opening_hours_tuesday`  
**Data type and size:** String (50)  
**Description:** A free text description of the Tuesday opening hours of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** If `opening_hours_tuesday` is true then a value must be present.  
**Validation implementation:** String.  
**Example:** `09:00-12:30`, `13:00-18:00`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 60. Opening Hours Wednesday
**Field name:** `opening_hours_wednesday`  
**Data type and size:** String (50)  
**Description:** A free text description of the wednesday opening hours of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** If `opening_hours_wednesday` is true then a value must be present.  
**Validation implementation:** String.  
**Example:** `09:00-12:30`, `13:00-18:00`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 61. Opening Hours Thursday
**Field name:** `opening_hours_thursday`  
**Data type and size:** String (50)  
**Description:** A free text description of the Monday opening hours of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** If `opening_hours_thursday` is true then a value must be present.  
**Validation implementation:** String.  
**Example:** `09:00-12:30`, `13:00-18:00`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 62. Opening Hours Friday
**Field name:** `opening_hours_friday`  
**Data type and size:** String (50)  
**Description:** A free text description of the Monday opening hours of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** If `opening_hours_friday` is true then a value must be present.  
**Validation implementation:** String.  
**Example:** `09:00-12:30`, `13:00-18:00`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 63. Opening Hours Saturday
**Field name:** `opening_hours_saturday`  
**Data type and size:** String (50)  
**Description:** A free text description of the Monday opening hours of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** If `opening_hours_saturday` is true then a value must be present.  
**Validation implementation:** String.  
**Example:** `09:00-12:30`, `13:00-18:00`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 64. Opening Hours Sunday
**Field name:** `opening_hours_sunday`  
**Data type and size:** String (50)  
**Description:** A free text description of the Monday opening hours of the food business.  
**Source:** Data entered by the user.  
**Validation rules:** If `opening_hours_sunday` is true then a value must be present.  
**Validation implementation:** String.  
**Example:** `09:00-12:30`, `13:00-18:00`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 65. Food Business Premises
**Field name:** `premise`  
**Data type and size:** Data structure  
**Description:** This data structure conatins data about the food business premises. The establishment address is intended to be processed in one of two ways:
1. Use the `establishment_uprn` to match the address to your own address gazetteer records.
2. Construct the address using the address label fields; `establishment_address_line_1`, `establishment_address_line_2`, `establishment_address_line_3`, `establishment_town`, `establishment_postcode`.
**Source:** N/A.  
**Validation rules:** N/A.  
**Validation implementation:** N/A.  
**Example:** N/A.  
**Personal data:** N/A.  
**Data sent in notification emails:** Yes.  

### 66. Establishment Address First Line
**Field name:** `establishment_first_line`  
**Data type and size:** String (256)  
**Description:** This is a legacy field, and is still presented within the data standard for any legacy integrations. This field may be removed from the standard at a later date and should not be used in new integrations. This field is currently a mirror of `establishment_address_line_1`.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `612`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 67. Establishment Address Street
**Field name:** `establishment_street`  
**Data type and size:** String (256)  
**Description:** This is a legacy field, and is still presented within the data standard for any legacy integrations. This field may be removed from the standard at a later date and should not be used in new integrations. This field is currently a mirror of `establishment_address_line_2`.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `Newport Road`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 68. Establishment Address Locality
**Field name:** `establishment_dependent_locality`  
**Data type and size:** String (256)  
**Description:** This is a legacy field, and is still presented within the data standard for any legacy integrations. This field may be removed from the standard at a later date and should not be used in new integrations. This field is currently a mirror of `establishment_address_line_3`.  
**Source:** Data entered or confirmed by user.  
**Validation rules:** Optional.  
**Validation implementation:** ASCII String.  
**Example:** `Shotley Gate`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 69. Establishment Address Label Line 1
**Field name:** `establishment_address_line_1`  
**Data type and size:** String (256)  
**Description:** The establishment address label line 1 is an alternative presentation of the address that combines required PAF fields into an address label. The service can return any address in a specific number of lines, we request three.  
**Source:** Data returned by postcode lookup.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `Flat 2`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 70. Establishment Address Label Line 2
**Field name:** `establishment_address_line_2`  
**Data type and size:** String (256)  
**Description:** The establishment address label line 2 is an alternative presentation of the address that combines required PAF fields into an address label. The service can return any address in a specific number of lines, we request three.  
**Source:** Data returned by postcode lookup.  
**Validation rules:** May be present.  
**Validation implementation:** ASCII String.  
**Example:** `612 Newport Road`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 70. Establishment Address Label Line 3
**Field name:** `establishment_address_line_3`  
**Data type and size:** String (256)  
**Description:** The establishment address label line 3 is an alternative presentation of the address that combines required PAF fields into an address label. The service can return any address in a specific number of lines, we request three.  
**Source:** Data returned by postcode lookup.  
**Validation rules:** May be present.  
**Validation implementation:** ASCII String.  
**Example:** `Shotley Gate`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 72. Establishment Address Town
**Field name:** `establishment_town`  
**Data type and size:** String (256)  
**Description:** The town of the food business address. Data retrieved from the address record supplied by API call to the lookup service or entered by the user.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** ASCII String.  
**Example:** `Cardiff`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 73. Establishment Address Postcode
**Field name:** `establishment_postcode`  
**Data type and size:** String (8)  
**Description:** The postcode of the food business address.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** String `npm validator isPostalCode (GB)`  
**Example:** `CF99 6TR`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 74. Establishment Address UPRN
**Field name:** `establishment_uprn`  
**Data type and size:** String (12)  
**Description:** The Unique Property Reference Number of the food business address.  Data retrieved from the address record supplied by API call to the lookup service.  
**Source:** Data entered by the user.  
**Validation rules:** Optional, but desirable.  May be missing in edge cases where address was not found in postcode lookup.  
**Validation implementation:** N/A. Generated during postcode lookup.  
**Example:** `824683234325`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 75. Establishment Type
**Field name:** `establishment_type`  
**Data type and size:** String (50)  
**Description:** Selected by the user from three options: `Place of business or commercial premises`, `Mobile or moveable premises`, `Home or domestic premises`.  
**Source:** Data entered by the user.  
**Validation rules:** Must be present.  
**Validation implementation:** N/A. Selected via radio button in the service.  
**Example:** `Mobile or moveable premises`  
**Personal data:** No.  
**Data sent in notification emails:** Yes.  

### 76. Declaration
**Field name:** `metadata`  
**Data type and size:** A data structure that contains the declaration data fields. This structure is likely to be removed in a future release and the declaration data fields placed in the top-level registrations structure.  
**Description:** N/A.  
**Source:** N/A.  
**Validation rules:** N/A.  
**Validation implementation:**  N/A.
**Example:** N/A.  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 77. Declaration 1
**Field name:** `declaration1`  
**Data type and size:** String  
**Description:** The user must tick agreement to this preset declaration.  
**Source:** The user ticks a box to confirm that they agree to this statement.  
**Validation rules:** Declaration text must be present in a food business registration record.  
**Validation implementation:** User agreement captured in the service.  
**Example:** `I declare that the information I have given on this form is correct and complete to the best of my knowledge and belief.`  
**Personal data:** Y  
**Data sent in notification emails:** Yes.  

### 78. Declaration 2
**Field name:** `declaration2`  
**Data type and size:** String  
**Description:** The user must tick agreement to this preset declaration.  
**Source:** The user ticks box to confirm that they agree to this statement.  
**Validation rules:** Declaration text must be present in a food business registration record.  
**Validation implementation:** User agreement captured in the service.  
**Example:** `The operator will notify their LA of any significant changes to the business activity, including closure, within 28 days of the change happening.`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  

### 79. Declaration 3
**Field name:** `declaration3`  
**Data type and size:** String  
**Description:** The user must tick agreement to this preset declaration.  
**Source:** Food business operator user ticks box to confirm that they agree to this statement.  
**Validation rules:** Declaration text must be present in a food business registration record.  
**Validation implementation:** User agreement captured in the service.  
**Example:** `The operator understands they are legally responsible for the safety and authenticity of the food being produced or served at this establishment.`  
**Personal data:** Yes.  
**Data sent in notification emails:** Yes.  
