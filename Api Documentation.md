# Register a Food Business Collections API v1.4 : Developer Guidance

### 1. Contents:

This document provides developer guidance on the Food Standards Agency Register a food business (RAFB) Collections API. The guidance is written for developers and systems administrators. It is expected to be of interest to local authorities in England, Wales and Northern Ireland, and to their management information systems software providers. The documentation provides information on the following areas.
1.  [Introduction](#2-introduction)
2.  [API Reference](#3-api-reference)
3.  [Getting Started](#4-getting-started)
4.  [Live Support](#5-live-support)
5.  [Development Roadmap](#6-development-roadmap)
6.  [Contact Us](#7-contact-us)


This version of the document is current as at 20th February 2020. In API v1.4 a small number of additional data fields have been
made available through the API.

***

### 2 Introduction

#### Regulatory Background
The **Register a food business service** is a partnership between the Food Standards Agency and local authorities across England, Wales and Northern Ireland. The service improves the registration user experience for food business operators and captures highquality data for regulatory use.

New food business operators have a legal obligation to register with their local authority. This digital service enables them to identify their local authority and apply to register with them. The current main access point for food business operators is via [GOV.UK](https://www.gov.uk/food-business-registration) or the web sites of individual local authorities, with links from [food.gov.uk](https://www.food.gov.uk/business-guidance/register-a-food-business) to be added.

#### The Purpose of the Collections API
Local authorities can then collect these registrations through the **Register a food business collections API** described in this documentation. An API is an Application Programming Interface that provides a standard mechanism to collect data in an easy to use data format. The data collected through the API can be imported into local authority management information systems for follow-up activities (including an inspection of the establishment) to be scheduled.


#### How the Collections API Works
 Food business registrations are captured on the Register a Food Business web site for each local authority and stored in a database until collected. The registrations are available for collection by the local authority using the collections API.

Each local authority using the service must integrate its management information systems (MIS) with the collections API. The local authority must get access to the API and must be able to process the data collected. This work can be done by a local digital team, or by acquiring products or services with this capability.


The collections API is used as follows.

*   The local authority MIS makes its first API call to collect all new registrations for that local authority. In doing so it must supply an API key which is used to authorise access. The data is returned as an array of JSON data containing any new registrations.
*   The local authority MIS must process each registration in turn. At this stage we ask that a second API call is made to confirm that the registration has been collected. This second API call updates a collection flag in the RAFB database and ensures that the data will not be supplied again at the next request for new registrations.
*   The final step is the processing of the registration within the local authority, checking that the registration is genuine and not duplicate, and setting up the local authority workflow for follow-up activity include inspection of the food business premises.

This sequence diagram summarises the collections process in the beta RAFB Collections API.

![sequence diagram for the collections process in the beta RAFB Collections API](https://raw.githubusercontent.com/fsadata/RegisterAFoodBusinessDataStandard/master/images/CollectionsProcessSequenceDiagram.PNG "sequence diagram for the collections process in the beta RAFB Collections API")

Please refer to the [API Reference](#3-api-reference) section of this documentation for more detail on the API operations.

#### How the Collections API is Accessed
The API is internet-facing. API calls must use a specific URL for each local authority, and supply the correct API Key. API users can log in and manage their API Key as part of their account and subscription information in the API gateway portal. Two API keys (primary, secondary) are provided for each subscription and either can be used.

The API is accessed through an API gateway as follows:

*   The integration test gateway is at [https://integration-fsa-rof-gateway.azure-api.net](https://integration-fsa-rof-gateway.azure-api.net) with a developer portal (for documentation and API key management) at [https://integration-fsa-rof-gateway.portal.azure-api.net](https://integration-fsa-rof-gateway.portal.azure-api.net).

*   The production gateway is at [https://fsa-rof-gateway.azure-api.net](https://fsa-rof-gateway.azure-api.net) with a developer portal (for API key management) at [https://fsa-rof-gateway.portal.azure-api.net](https://fsa-rof-gateway.portal.azure-api.net)
*   The current URLs reflects the API gateway service on the Microsoft Azure cloud platform. We haven’t allocated a separate sub-domain for this API but may do so before the end of the beta phase of the project. (e.g. `api.registrations.food.gov.uk` and `test-api.registrations.food.gov.uk`).

#### API Versioning

The API is versioned using a major/minor version scheme.

*   Major API versions (e.g. v1) will be built into the API URL, for example: `https://{api-gateway}/registrations/v1/{local-authority}`. A new major version will be used for changes that break compatibility with the previous version of the API.
*   Minor API versions (e.g. v1.3) will not be built into the URL.
*   The project team maintain a change log of versions.

#### API Conditions of Use

The API is targeted at use by partner organisations rather than the public or food businesses directly. It should be viewed as a collaborative partnership with local authorities to drive better quality data and outcomes. There is no charge to local authorities to use the Register a Food Business Service. The main legal requirement around use of the production API is that terms of service including a data sharing agreement are agreed between the Food Standards Agency (FSA) and each local authority (LA) that receives the data. The LA-side of the data sharing agreement covers the controls in place across the LA and any MIS provider products and services it uses.

#### Current Status of the Register a Food Business Service
The Register a food business service is in the [beta phase](https://www.gov.uk/service-manual/agile-delivery/how-the-beta-phase-works) of development. It is a working service that captures real food business registrations and makes them available to live systems at local authorities. In the next development phase, the service will move from a private beta (minimum viable product used by a small set of local authorities and their management information systems provider) to a public beta (available to all local authorities, digital teams and management information systems providers). A date for transition from beta to live service has not been set.


#### Working together to implement the collections API

To use the collections API, you will need to engage with the Register a Food Business project team – [Contact Us](#7-contact-us) and work through the information in the [Getting Started](#4-getting-started) section.

***

### 3 API Reference

#### Link to Full Open API Reference Documentation
The RAFB Collections API is a RESTful API that has been built to meet the [Open API standard](https://swagger.io/docs/specification/about/) using the Swagger editor.

The most recent specification can be downloaded from the [Integration Test API Gateway](https://integration-fsa-rof-gateway.portal.azure-api.net/) site where you see the icon on screen. The RAFB Collections API can be downloaded as an Open API 2.0 JSON definition that can be uploaded into the [Swagger editor](https://editor.swagger.io/) to view as interactive documentation.

#### Summary of API Calls
The API calls are summarised below.

| Operation | API Call | Parameters | HTTP Headers | Response |
| --- | --- | --- | --- | --- |
| Get All New Food Business Operator Registrations for the Local Authority | GET `https://{apigateway}/registrations/{version}/{localauthority}` | `fields={array}` `new={boolean}` | `Ocp-ApimSubscriptionKey={key}` | HTTP Status code and JSON array of registrations data. |
| Get Single Food Business Operator Registration | GET `https://{apigateway}/registrations/{version}/{localauthority}/{fsa-rn}` | None | `Ocp-ApimSubscriptionKey={key}` | HTTP Status code and JSON registrations data. |
| Update Single Food Business Operator Registration Collected | PUT `https://{apigateway}/registrations/{version}/{localauthority}/{fsa-rn}` | Data (to set collection flag value) `{“collected”:true}` | `Ocp-ApimSubscriptionKey={key}` | HTTPS Status code and JSON data confirming collection flag value. |

URLs are built using the following information.

|   |   |   |
|-----------|----------|------------|
| api-gateway | Integration Test Gateway | <https://integration-fsa-rof-gateway.azure-api.net> |
| api-gateway | Production Gateway | <https://fsa-rof-gateway.azure-api.net> |
| local-authority | Local Authority | The local authority for the registration |
| version | Major version of API | The API major version e.g. v1 which incorporates versions 1.0, 1.1, 1.2 etc. |
| fsa-rn | FSA Reference Number | The transaction reference number for each registration |
| fields={array} | Parameter to specify data to include | Specifying value `fields=establishment,metadata` returns the full data set when collecting all new registrations. |
| new={boolean} | Parameter to collect new registrations | Value `new=true` means collect only new registrations which have not been marked as collected. This is the default value is the parameter is omitted. Value `new=false` means collect all registrations. |
| API Header Information | Must include the API Key | To use the primary key, include `Ocp-Apim-Subscription-Key={primary-key}` To use the secondary key instead, change the key `Ocp-Apim-SubscriptionKey={secondary-key}` |

#### Guidance on the RAFB Registrations data

The data returned in a registrations data set can be found in the [Data standard](https://github.com/fsadata/RegisterAFoodBusinessDataStandard/blob/master/Data%20Standard.md) stored in this repository

#### API Example

This is an example of how the API calls are assembled.

| Configuration |  | Example Data |
| --- | --- | --- |
| api-gateway | Integration Test Gateway | <https://integration-fsa-rof-gateway.azure-api.net> |
| api-gateway | Production Gateway | <https://fsa-rof-gateway.azure-api.net> |
| local-authority | Wintervale Borough Council | wintervale |
| version | API version 1.1 | v1 |
| fsa-rn | FSA Reference Number | AHFGHL-CNFVJQ-D6H8BH |

| API Operation | Example API Call | HTTP Headers |
| --- | --- | --- |
| **Example** Get All New Food Business Operator Registrations for Wintervale Borough Council returning the establishment data | Test API `GET https://integration-fsa-rof-gateway.azureapi.net/registrations/v1/wintervale?fields=establishment&new=true`  Production API `GET https://fsa-rof-gateway.azureapi.net/registrations/v1/wintervale?fields=establishment&new=true` | Ocp-ApimSubscription-Key=e567ed19c79b46c48adf0e59f4573a3e |
| Example Update Single Food Business Operator Registration AHFGHLCNFVJQ-D6H8BH received by Wintervale Borough Council to collected status | Production API `PUT https://fsa-rof-gateway.azureapi.net/registrations/v1/wintervale/AHFGHL-CNFVJQ-D6H8BH`  Data provided (to set collection flag value) `{“collected”: true}` | Ocp-ApimSubscription-Key=e567ed19c79b46c48adf0e59f4573a3e |

***

### 4. Gettting Started

This section explains how to get started with the Register a food business collections API a developer.

Firstly please [Get in touch](#7-contact-us) with the project team to let us know about your interest.

[Register](https://integration-fsa-rof-gateway.portal.azure-api.net/signup) for a developer account on our Integration Test API Developer Portal. We can set up the account for you but suggest that you start this so as to setup and maintain your password through the portal.
![Integration Test Api Developer Portal](https://raw.githubusercontent.com/fsadata/RegisterAFoodBusinessDataStandard/master/images/IntegrationTestApiDeveloperPortal.PNG "Integration Test Api Developer Portal")

You will need to give us:
*   email address at your organisation,
*   your first name and last name,
*   and set a password.

We will set up a subscription to a test API containing:

*   a primary and secondary API key,
*   URL for a test local authority,
*   some test data consisting of a set of food business registrations.

You can then log in to the [Integration Test API Developer Portal](https://integration-fsa-rof-gateway.portal.azure-api.net/signin?ReturnUrl=%2F) to obtain your API keys and try out the API. The main functions of the developer portal are listed below.

| API Gateway Developer Portal Functions | Description |
| --- | --- |
| Change account information, Change password, View subscriptions, Show API Keys for subscription, Regenerate API Keys | Click on your name and then PROFILE to access this page ![Screenshot of the API profile page](https://raw.githubusercontent.com/fsadata/RegisterAFoodBusinessDataStandard/master/images/DeveloperPortalProfilePage.PNG "Screenshot of the API profile page") |
| View information for a version of an API URL, Parameters, Headers, Responses Code Samples (Auto generated – we have not tested these) | Click on APIS and select the API version that you want to view which then displays this screen. ![Screenshot of the API page](https://raw.githubusercontent.com/fsadata/RegisterAFoodBusinessDataStandard/master/images/DeveloperPortalApiInformation.PNG "Screenshot of the API page") |
| Download API Definition Open API 2 JSON, We have not tested the auto generated Open API 3 or WADL definitions | Click on the button to access this download. ![Api Definition Button](https://raw.githubusercontent.com/fsadata/RegisterAFoodBusinessDataStandard/master/images/DeveloperPortalApiDefinitionButton.PNG "Api Definition Button") |
| Try the API. Test and learn about the API from within the developer portal using your API key. | ![Try It Button](https://raw.githubusercontent.com/fsadata/RegisterAFoodBusinessDataStandard/master/images/DeveloperPortalTryIt.PNG "Try It Button") Click on the Try It button to access the page where you can add/remove and enter values for query parameters and header values, set which API key (primary or secondary) to use, view the HTTP request and the Response Status and Content. Example screen shots are provided below. ![Try It Page](https://raw.githubusercontent.com/fsadata/RegisterAFoodBusinessDataStandard/master/images/DeveloperPortalTryItPage.PNG "Try It Page") |

Now code your application using what you have learned. Use the integration test gateway to test. Talk to us about more test data and any specific testing that you need to do.

When satisfied that your integration with the collections API is complete, we need to repeat the setup process on the production API portal for you to obtain the production API key, update your application configuration to use production URL and API key, and perform end-to-end test registrations with us to verify that the API works as designed.

The service can now be implemented as a production service. The Register a food business front-end URL for the local authority will be implemented and linked to from external sites so that food business operators will be signposted to the site to register.

***

### 5 Live Support

The Food Standards Agency have a service desk team to capture information on support incidents and route to the appropriate application support teams to investigate further. As part of the implementation of the Register a Food Business web sites, contact details for each local authority are entered into the service desk IT system (Service Now) so that incidents and service requests can be tracked and co-ordinated. The project team will work with you to implement the routing for support calls.

The current service desk operation (provided by Littlefish) is available 24 x 7. The application support capability for Register a Food Business is only available during office hours Monday to Friday.

#### Live Service Measures and Controls

The Availability design goal is for the RAFB production API to be available 99.9% of the time, which matches the availability of the underlying cloud infrastructure components.

Subscription **Rate limits** for subscriptions will be reviewed. The current working assumptions for the production system are that registrations:
*   Will be collected at least one per day for each local authority,
*   Can be collected once per hour and will not be collected more frequently than this.

Finally, Information Security controls will continue to be actively managed by the Foods Standards Agency and its IT partners, including periodic external IT Health Check review of the system.

***

### 6 Development Roadmap

This section highlights those parts of the API that may be developed further, and those areas on which we intend to consult further with the developer community.

#### What’s New in API version 1.4

RAFB API 1.4 is a minor update to add the following additional data items.

| Data Item | Data Type | Description | Example |
| --- | --- | --- | --- |
| competent_authority_id | String (4) | Competent authority identifier. This is configuration data that originates from the register of competent authorities (Local Authorities and Port Health Authorities) <https://data.food.gov.uk/codes/reference-number/_authority> | `8002`, `6009` |
| local_council_url | String (50) | Local Authority URL. This is configuration data identifying the URL name for the local authority | `the-vale-ofglamorgan`, `mid-ulster` |
| operator_address_line_1 | String (256) | Operator Address Label Line 1. Alternative presentation of address premises, thoroughfare, double dependent locality and dependent locality data returned by postcode lookup as a 3-line address label. | `Flat 2` |
| operator_address_line_2 | String (256) | Operator Address Label Line 2. Alternative presentation of address premises, thoroughfare, double dependent locality and dependent locality data returned by postcode lookup as a 3-line address label. | `612 Newport Road` |
| operator_address_line_3 | String (256) | Operator Address Label Line 3. Alternative presentation of address premises, thoroughfare, double dependent locality and dependent locality data returned by postcode lookup as a 3-line address label. | `Shotley Gate` |
| establishment_address_line_1 | String (256) | Establishment Address Label Line 1. Alternative presentation of addresa premises, thoroughfare, double dependent locality and dependent locality data returned by postcode lookup as a 3-line address label. | `Flat 2` |
| establishment_address_line_2 | String (256) | Establishment Address Label Line 2. Alternative presentation of address premises, thoroughfare, double dependent locality and dependent locality data returned by postcode lookup as a 3-line address label. | `612 Newport Road` |
| establishment_address_line_3 | String (256) | Establishment Address Label Line 3. Alternative presentation of address premises, thoroughfare, double dependent locality and dependent locality data returned by postcode lookup as a 3-line address label. | `Shotley Gate` |

The local authority identifier data links to our register of competent authorities. The new address fields allow for an alternative presentation of addresses. Addresses can be processed in one of three ways.
1. Use the uprn (Unique Property Reference Number) to match the address to your own address gazetteer records.
2. Use Royal Mail PAF fields (not all PAF fields are supplied): `first_line`, `street`, `dependent_locality`, `town`, `postcode`.
3. Use Address Label fields: `address_line_1`, `address_line_2`, `address_line_3`, `town`, `postcode`.

#### API Features

We are seeking feedback on the API design and operation. The API must be easy to work with. We will check with the developer community on what additional features and support will improve their experience of working with the Register a Food Business service.

#### API Definition

The API currently supplies additional id and datetime fields in the data output. These fields are not referenced in the API guidance earlier in this document. As these are part of the internal data set and not useful to external developers, they will be removed from the data output in a forthcoming API release: `establishment.id`, `establishment.createdAt`, `establishment.updatedAt`, `establishment.registrationId`, `operator.id`, `operator.createdAt`, `operator.updatedAt`, `operator.establishmentId`, `activities.id`, `activities.createdAt`, `activities.updatedAt`, `activities.establishmentId`, `premise.id`, `premise.createdAt`, `premise.updatedAt`, `premise.establishmentId`, `metadata.id`, `metadata.createdAt`, `metadata.updatedAt`, `metadata.registrationId`.

#### API Security
The project team is investigating whether additional API security controls (for example adding an OAuth authorisation step to generate a token) are desirable or necessary, and to identify what should be added to the beta collections API. We will consult with the developer community on this area to examine trade-offs and seek consensus.

#### Data Quality

We are monitoring data quality to identify whether additional improvements to further improve the quality of registrations data are necessary. The project team will consult in general on this, but also on specific aspects. These includes a look at how we can improve our management of reference data (e.g. local authority configurations, business types, preparation for the future addition of welsh language support). We need to explore the known issue of duplicate food business registrations, where a food business operator registers through Register a Food Business but already has a registration held by the local authority that has been made through a different channel.

#### Service Dashboard
The project team intend to provide a Register a Food Business service dashboard that tracks the numbers of registrations and API calls. We will consult on features, including whether variants would be useful for:
*   individual local authorities
*   management information systems providers supporting multiple local authorities.

#### API Versions

We will consult on the anticipated time frames for implementing future API changes and for deprecating old versions.

***

### 7 Contact Us
The first point of contact for information about the API is the Register a Food Business project team in the Food Standards Agency who can be reached via the email address [FutureDelivery@food.gov.uk](mailto:FutureDelivery@food.gov.uk).
