FORMAT: 1A

# FX Hello

# Categories [/categories]
Categories related operations.

## Categories [POST /categories]
Returns the full list of categories

+ Parameters
    + type: (integer, optional) - Type id of the category
    + subType: (integer, optional) - Sub-type id of the category

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 7,
                "subType": null
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5801b8184189dc69ad440a0c",
                "oldid": "5703128158568448",
                "oid": 102,
                "name": "New Raw material",
                "parent": null,
                "type": 20,
                "status": 1,
                "meta": {
                    "description": "",
                    "category_code": ""
                },
                "cuid": 6,
                "uuid": 6,
                "created_at": "2016-09-15 08:13:49",
                "updated_at": "2016-09-15 08:13:49"
            }

## Category [POST /categories/category]
Returns the information of a category

+ Parameters
    + id: (string, required) - ID of the category that needs to be retrieved.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "5801b8184189dc69ad440a0c"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5837ed6158e13f6ff6296142",
                "oid": 102,
                "type": 20,
                "parent": "5801c7ed4189dc6a8212d84a",
                "name": "Demo234",
                "status": 1,
                "meta": {
                    "description": "New material",
                    "category_code": ""
                },
                "cuid": 6,
                "uuid": 6,
                "created_at": "2016-11-25 07:50:57",
                "updated_at": "2016-11-25 07:50:57"
            }

## Categories by ID's [POST /categories/categories]
Returns the information of a collection of categories by their IDs

+ Parameters
    + ids: (string, required) - IDs of categories as a comma separated string

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "ids": "5801b8184189dc69ad440a0c, 5837ed6158e13f6ff6296142, 583c083258e13f18660d3732"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "5801b8184189dc69ad440a0c",
                    "oldid": "5703128158568448",
                    "oid": 102,
                    "name": "New Raw material",
                    "parent": null,
                    "type": 20,
                    "status": 1,
                    "meta": null,
                    "cuid": 6,
                    "uuid": 6,
                    "created_at": "2016-09-15 08:13:49",
                    "updated_at": "2016-09-15 08:13:49",
                    "description": null,
                    "color": null,
                    "code": null
                },
                {
                    "_id": "5837ed6158e13f6ff6296142",
                    "oid": 102,
                    "type": 20,
                    "parent": "5801c7ed4189dc6a8212d84a",
                    "name": "Demo234",
                    "status": 1,
                    "meta": null,
                    "cuid": 6,
                    "uuid": 6,
                    "created_at": "2016-11-25 07:50:57",
                    "updated_at": "2016-11-25 07:50:57",
                    "description": "New material",
                    "color": null,
                    "code": null
                },
                {
                    "_id": "583c083258e13f18660d3732",
                    "oid": 102,
                    "type": 20,
                    "parent": "5801c7ed4189dc6a8212d84a",
                    "name": "BMW car",
                    "status": 1,
                    "meta": null,
                    "cuid": 1652,
                    "uuid": 1652,
                    "created_at": "2016-11-28 10:34:26",
                    "updated_at": "2016-11-28 10:34:26",
                    "description": null,
                    "color": null,
                    "code": "157428df"
                }
            ]

## Create a category [POST /categories/create]
Allows the user to create a category

+ Parameters
    + type: (integer, required) - Type of the category
    + subType: (integer, optional) - Sub-type of the category
    + parent: (string, optional) - ID of the parent category
    + name: (string, required) - Name of the category
    + key: (string, optional) - Key of the category. Lowercase hyphenated string
    + description: (string, optional) - Description of the category
    + color: (string, optional) - Color of the category as a hex string, with hash sign.
    + status: (integer, optional) - Status of the category
        + Default: 1

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "name": "Apples 0605",
                "type": "7",
                "key": "apples-0605",
                "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "color": "#1a2b3c",
                "status": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5934e45d4189dc4e1e4f60b2",
                "oid": 102,
                "type": 7,
                "subType": null,
                "parent": null,
                "name": "Apples 0605",
                "key": "apples-0605",
                "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "color": "#1a2b3c",
                "status": "1",
                "cuid": 1618,
                "cuName": "John",
                "uuid": 1618,
                "uuName": "John",
                "updated_at": "2017-06-05 04:55:57",
                "created_at": "2017-06-05 04:55:57"
            }

## Update a category [POST /categories/categories/update]
Allows the user to update the existing information of a category

+ Parameters
    + id: (string, required) - ID of the category
    + name: (string, optional) - Name of the category
    + key: (string, optional) - Key of the category. Lowercase hyphenated string
    + description: (string, optional) - Description of the category
    + color: (string, optional) - Color of the category as a hex string, with hash sign.
    + status: (integer, optional) - Status of the category

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "5801b8184189dc69ad440a0c"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "57fdc2006b0bdc7d6809b522",
                "oid": 102,
                "type": 4,
                "name": "New contact cat",
                "created_at": "2016-10-12 04:54:24",
                "cuid": 6,
                "uuid": 1,
                "status": 1,
                "updated_at": "2017-06-02 10:39:59",
                "parent": null,
                "key": null,
                "description": null,
                "color": null,
                "uuName": "John"
            }

# CRM - Customers [/crm/customers]
CRM related operations for Customers, Contacts, and their groups.

## Customers [POST /crm/customers]
Returns the full list of customers

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

## Customer profile [POST /crm/customers/customer]
Returns the information of a customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Create customer [POST /crm/customers/customer/create]
Create a new customer for the organization

+ Parameters
    + subType: (integer, optional) - 1: Company, 2: Individual
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + prefix: (string, optional) - Mr., Mrs., Miss, Dr., etc. Retrieve list from API
    + telephones: (array, optional) - 
    + mobile: (string, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + website: (string, optional) - 
    + address1: (string, optional) - 
    + address2: (string, optional) - 
    + city: (string, optional) - 
    + stateID: (string, optional) - 
    + zip: (string, optional) - 
    + country: (integer, optional) - 
    + description: (string, optional) - 
    + designation: (string, optional) - 
    + categories: (array, optional) - 
    + customerSince: (date, optional) - Date as a string in the format of YYYY-mm-dd
        + Default: 2017-06-23
    + leadSourceID: (string, optional) - 
    + creditLimit: (string, optional) - 
    + creditPeriod: (string, optional) - 
    + industries: (array, optional) - 
    + marketingCampaigns: (array, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Edit customer [POST /crm/customers/customer/update]
Edit/update a customer information.

+ Parameters
    + id: (string, required) - Customer ID
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + prefix: (string, optional) - Mr., Mrs., Miss, Dr., etc. Retrieve list from API
    + telephones: (array, optional) - 
    + mobile: (string, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + website: (string, optional) - 
    + address1: (string, optional) - 
    + address2: (string, optional) - 
    + city: (string, optional) - 
    + stateID: (string, optional) - 
    + zip: (string, optional) - 
    + countryID: (integer, optional) - 
    + description: (string, optional) - 
    + designation: (string, optional) - 
    + categories: (array, optional) - 
    + customerSince: (date, optional) - Date as a string in the format of YYYY-mm-dd
        + Default: 2017-06-23
    + leadSourceID: (string, optional) - 
    + creditLimit: (string, optional) - 
    + creditPeriod: (string, optional) - 
    + industries: (array, optional) - 
    + marketingCampaigns: (array, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer support tickets [POST /crm/customers/customer/support]
Returns the support tickets that belongs to a provided customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer notes [POST /crm/customers/customer/notes]
Returns the notes that belongs to a provided customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer contacts [POST /crm/customers/customer/contacts]
Returns the contacts that are associated with the customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer opportunities [POST /crm/customers/customer/opportunities]
Returns the opportunities that belongs to a provided customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer quotations [POST /crm/customers/customer/quotations]
Returns the quotations that belongs to a provided customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer invoices [POST /crm/customers/customer/invoices]
Returns the invoices that belongs to a provided customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer sales orders [POST /crm/customers/customer/sales-orders]
Returns the sales orders that belongs to a provided customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Customer work orders [POST /crm/customers/customer/work-orders]
Returns the work orders that belongs to a provided customer

+ Parameters
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

# CRM - Contacts [/crm/contacts]
CRM Contacts related operations.

## Contact list (all) [POST /crm/contacts]
Returns all the contacts of the organization

+ Parameters
    + id: (string, required) - ID of the contact

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Individual contact [POST /crm/contacts/contact]
Returns the information of a contact by passing the ID

+ Parameters
    + id: (string, required) - ID of the contact

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Create contact [POST /crm/contacts/contact/create]
Create a new contact

+ Parameters
    + type: (integer, optional) - 3: Belongs to a customer, 4: Individual
        + Default: 4
    + typeid: (string, optional) - ID of the above type if applicable
    + subType: (integer, optional) - 1: General contact, 2: Customer contact
    + prefix: (string, optional) - Mr., Mrs., Miss, Dr., etc. Retrieve list from API
    + firstName: (string, optional) - 
        + Default: 
    + middleName: (string, optional) - 
        + Default: 
    + lastName: (string, optional) - 
        + Default: 
    + dob: (date, optional) - Date format YYYY-mm-dd
    + telephones: (array, optional) - 
    + mobile: (string, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + website: (string, optional) - 
    + address1: (string, optional) - 
    + address2: (string, optional) - 
    + city: (string, optional) - 
    + stateID: (string, optional) - 
    + zip: (string, optional) - 
    + countryID: (integer, optional) - 
    + description: (string, optional) - 
    + title: (string, optional) - 
    + categories: (array, optional) - 
    + marketingCampaigns: (array, optional) - 
    + leadSourceID: (string, optional) - 
    + department: (string, optional) - 
    + contactType: (string, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

## Update contact [POST /crm/contacts/contact/create]
Update a contact

+ Parameters
    + id: (string, required) - ID of the contact that is to be updated
    + prefix: (string, optional) - Mr., Mrs., Miss, Dr., etc. Retrieve list from API
    + firstName: (string, optional) - 
        + Default: 
    + middleName: (string, optional) - 
        + Default: 
    + lastName: (string, optional) - 
        + Default: 
    + title: (string, optional) - 
    + dob: (date, optional) - Date format YYYY-mm-dd
    + telephones: (array, optional) - 
    + mobile: (string, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + website: (string, optional) - 
    + address1: (string, optional) - 
    + address2: (string, optional) - 
    + city: (string, optional) - 
    + stateID: (string, optional) - 
    + zip: (string, optional) - 
    + countryID: (integer, optional) - 
    + description: (string, optional) - 
    + categories: (array, optional) - 
    + marketingCampaigns: (array, optional) - 
    + leadSourceID: (string, optional) - 
    + department: (string, optional) - 
    + contactType: (string, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

# CRM - Lead Sources [/crm/lead-sources]
CRM lead sources related operations for Customers, Contacts, and their groups.

## Lead sources [POST /crm/lead-sources]
Returns the full list of lead sources

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "5810752a6b0bdc094041d6e2",
                    "oid": 102,
                    "source": "Email"
                },
                {
                    "_id": "581ab09f58e13f433041dcc2",
                    "oid": 102,
                    "source": "Caller"
                }
            ]

## Lead source (single) [POST /crm/lead-sources/lead-source]
Returns the information of a lead source

+ Parameters
    + id: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5810752a6b0bdc094041d6e2",
                "oid": 102,
                "source": "Email"
            }

## Lead sources by IDs (multiple) [POST /crm/lead-sources/lead-sources]
Returns the information of a lead sources by passing in the Ids

+ Parameters
    + ids: (array, required) - Lead source IDs an an array or a comma seperated list
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "ids": "546813a68bc6, 1464a135be6, 6846fe65"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "5810752a6b0bdc094041d6e2",
                    "oid": 102,
                    "source": "Email"
                },
                {
                    "_id": "581ab09f58e13f433041dcc2",
                    "oid": 102,
                    "source": "Caller"
                }
            ]

## Create customer lead source [POST /crm/lead-sources/lead-source/create]
Create a new customer lead source for the organization

+ Parameters
    + source: (string, required) - Lead source name
        + Default: 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "source": "Expo XYZ",
                "status": 1
            }

## Update customer lead source [POST /crm/lead-sources/lead-source/update]
Update a customer lead source for the organization by passing in the ID of the lead source

+ Parameters
    + id: (string, required) - Lead source ID
        + Default: 
    + source: (string, optional) - Lead source name
        + Default: 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "5810752a6b0bdc094041d6e2",
                "source": "Expo XYZ",
                "status": 1
            }

# Tasks [/tasks]
Tasks related operations.

## List of tasks [POST /tasks]
Retrieve a full or filtered list of tasks. Result may subject to filtration based on user permission.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
            Content-Type: application/json
    + Body

            {
                "title": "This is the task name",
                "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "dueDate": "2017-10-23 14:23:00",
                "priority": 3,
                "type": 17,
                "typeId": "46ab4658f88e8d8",
                "subType": 1
            }

+ Response 200 (application/json)
    + Body

            {
                "type": 0,
                "typeid": 0,
                "subType": 0,
                "isTask": true,
                "title": "This is the task name",
                "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "dueDate": null,
                "priority": 3,
                "status": 1,
                "cuid": 1,
                "cuName": "John",
                "uuid": 1,
                "uuName": "John",
                "updated_at": "2017-05-18 05:05:12",
                "created_at": "2017-05-18 05:05:12",
                "_id": "591d2b884189dc52725cc042"
            }

## Create a new task [POST /tasks/create]
Allows the user the create a new task

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
            Content-Type: application/json
    + Body

            {
                "title": "This is the task name",
                "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "dueDate": "2017-10-23 14:23:00",
                "priority": 3,
                "type": 17,
                "typeId": "46ab4658f88e8d8",
                "subType": 1
            }

+ Response 200 (application/json)
    + Body

            {
                "type": 0,
                "typeid": 0,
                "subType": 0,
                "isTask": true,
                "title": "This is the task name",
                "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "dueDate": null,
                "priority": 3,
                "status": 1,
                "cuid": 1,
                "cuName": "John",
                "uuid": 1,
                "uuName": "John",
                "updated_at": "2017-05-18 05:05:12",
                "created_at": "2017-05-18 05:05:12",
                "_id": "591d2b884189dc52725cc042"
            }

# Device health [/devices/health]
Device health related monitoring and operation.

## Create health ping [POST /devices/health/create]
Create a new device health ping

+ Parameters
    + timestamp: (string, optional) - Format: Y-m-d H:m:s
        + Default: Current time stamp
    + gpsOn: (integer, optional) - 0:False, 1:True
    + gpsLat: (string, optional) - 
    + gpsLon: (string, optional) - 
    + gpsSignalStrength: (string, optional) - 
    + batteryPercentage: (string, optional) - 
    + dataOn: (integer, optional) - 0:False, 1:True
    + dataStrength: (string, optional) - 
    + gsmOn: (integer, optional) - 0:False, 1:True
    + gsmStrength: (string, optional) - 
    + macAddress: (string, optional) - 
    + status: (integer, optional) - 
        + Default: 1

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

## Create health ping [POST /devices/health/create-bulk]
Create a new device health ping

+ Parameters
    + payload: (string, optional) - JSON string array with parameters mentioned in single health ping
        + Default: Current time stamp

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

# Stores [/stores]
Stores related operations.

## Stores [POST /stores/stores]
Returns the full list of warehouses

+ Parameters
    + type: (string, optional) - The type of store that should be retrieved. If not defined, all stores will be returned.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 7
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5834226c6b0bdc4b0d33ef92",
                "oid": 102,
                "type": 7,
                "name": "Demo warehouse",
                "location": "New York",
                "addresses": {
                    "main": {
                        "address1": "123 Main Street",
                        "address2": "Block D",
                        "city": "Washington",
                        "state": "",
                        "stateid": null,
                        "zip": "20005",
                        "country": "United States",
                        "countryid": "232",
                        "description": "",
                        "status": 1,
                        "cuid": 1,
                        "uuid": 1,
                        "created_at": "2017-05-25 09:20:29",
                        "updated_at": "2017-05-25 09:20:29"
                    }
                },
                "telephone1": "2342",
                "telephone2": "234234",
                "fax": "1646542",
                "email": "demo@flatorb.com",
                "description": "",
                "image": "",
                "status": 1,
                "cuid": 1679,
                "uuid": 1679,
                "created_at": "2016-11-22 10:48:11",
                "updated_at": "2016-11-22 10:48:11"
            }

## Store [POST /stores/stores/store]
Returns the information of a store by passing its ID.

+ Parameters
    + id: (string, required) - Store ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "5834226c6b0bdc4b0d33ef92"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5834226c6b0bdc4b0d33ef92",
                "oid": 102,
                "type": 7,
                "name": "Demo warehouse",
                "location": "New York",
                "addresses": {
                    "main": {
                        "address1": "123 Main Street",
                        "address2": "Block D",
                        "city": "Washington",
                        "state": "",
                        "stateid": null,
                        "zip": "20005",
                        "country": "United States",
                        "countryid": "232",
                        "description": "",
                        "status": 1,
                        "cuid": 1,
                        "uuid": 1,
                        "created_at": "2017-05-25 09:20:29",
                        "updated_at": "2017-05-25 09:20:29"
                    }
                },
                "telephone1": "2342",
                "telephone2": "234234",
                "fax": "1646542",
                "email": "demo@flatorb.com",
                "description": "",
                "image": "",
                "status": 1,
                "cuid": 1679,
                "uuid": 1679,
                "created_at": "2016-11-22 10:48:11",
                "updated_at": "2016-11-22 10:48:11"
            }

## Create a store [POST /stores/stores/store/create]
Allows the user to create a category

+ Parameters
    + type: (integer, required) - Type of the store
    + subType: (integer, optional) - Sub-type of the store
    + name: (string, required) - Name of the store
    + location: (string, optional) - Location of the store
    + address1: (string, optional) - 
    + address2: (string, optional) - 
    + city: (string, optional) - 
    + state: (string, optional) - 
    + stateid: (string, optional) - 
    + zip: (string, optional) - 
    + country: (integer, optional) - 
    + addressDescription: (string, optional) - 
    + telephones: (array, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + description: (string, optional) - 
    + status: (integer, optional) - Status of the store
        + Default: 1

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "name": "Apples 0605",
                "type": "7",
                "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "status": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "oid": 102,
                "type": "7",
                "name": "Apples 0605",
                "location": null,
                "addresses": {
                    "main": {
                        "address1": null,
                        "address2": null,
                        "city": null,
                        "state": null,
                        "stateid": null,
                        "zip": null,
                        "country": null,
                        "countryid": null,
                        "description": null,
                        "status": 1
                    }
                },
                "fax": null,
                "email": null,
                "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "status": "1",
                "cuid": 1,
                "cuName": "John",
                "uuid": 1,
                "uuName": "John",
                "updated_at": "2017-06-05 09:27:27",
                "created_at": "2017-06-05 09:27:27",
                "_id": "593523ff4189dc4e1c7d3e52"
            }

## Update a store [POST /stores/stores/store/update]
Allows the user to update a store

+ Parameters
    + id: (string, required) - ID of the store
    + type: (integer, required) - Type of the store
    + subType: (integer, optional) - Sub-type of the store
    + name: (string, required) - Name of the store
    + location: (string, optional) - Location of the store
    + address1: (string, optional) - 
    + address2: (string, optional) - 
    + city: (string, optional) - 
    + state: (string, optional) - 
    + stateid: (string, optional) - 
    + zip: (string, optional) - 
    + country: (integer, optional) - 
    + addressDescription: (string, optional) - 
    + telephones: (array, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + description: (string, optional) - 
    + status: (integer, optional) - Status of the store
        + Default: 1

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "name": "Apples 0605",
                "type": "7",
                "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "status": "1"
            }

+ Response 200 (application/json)
    + Body

            {
                "oid": 102,
                "type": "7",
                "name": "Apples 0605",
                "location": null,
                "addresses": {
                    "main": {
                        "address1": null,
                        "address2": null,
                        "city": null,
                        "state": null,
                        "stateid": null,
                        "zip": null,
                        "country": null,
                        "countryid": null,
                        "description": null,
                        "status": 1
                    }
                },
                "fax": null,
                "email": null,
                "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "status": "1",
                "cuid": 1,
                "cuName": "John",
                "uuid": 1,
                "uuName": "John",
                "updated_at": "2017-06-05 09:27:27",
                "created_at": "2017-06-05 09:27:27",
                "_id": "593523ff4189dc4e1c7d3e52"
            }

# Weigh slip items [/stores/weigh-slips/weigh-slip/items]
Weigh slip related operations.

## Weigh slip items [POST /stores/weigh-slips/weigh-slip/items]
Returns the full list of items in a weigh slip byt the weigh slip ID

+ Parameters
    + id: (string, required) - Weigh slip ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "64613a6e13e3153f3f"
            }

+ Response 200 (application/json)
    + Body

            []

## Weigh slip item [POST /stores/weigh-slips/weigh-slip/items/item]
Returns an item in a weigh slip by the weigh slip item ID

+ Parameters
    + id: (string, required) - Weigh slip item ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "64613a6e13e3153f3f"
            }

+ Response 200 (application/json)
    + Body

            []

## Weigh slip item [POST /stores/weigh-slips/weigh-slip/items/create]
Returns an item in a weigh slip by the weigh slip item ID

+ Parameters
    + id: (string, required) - Weigh slip item ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "64613a6e13e3153f3f"
            }

+ Response 200 (application/json)
    + Body

            []

## Weigh slip item (bulk) [POST /stores/weigh-slips/weigh-slip/items/create-bulk]
Returns an item in a weigh slip by the weigh slip item ID

+ Parameters
    + id: (string, required) - Weigh slip item ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "64613a6e13e3153f3f"
            }

+ Response 200 (application/json)
    + Body

            []

# GRN [/stores/grns]
GRN related operations.

## GRNs [POST /stores/grns]
GRN list of the organization.

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

## GRN Profile [POST /stores/grns/grn]
GRN record information.

+ Parameters
    + id: (string, required) - GRN ID

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

## Create GRN [POST /stores/grns/grn/create]
Stocks information of the organization.

Products array can contain id, qty, pieces, unitPrice, discount, lineTotal as keys of the array element

+ Parameters
    + number: (string, optional) - GRN number
    + storeId: (string, required) - Store id of the store where the GRN is received to.
    + vendorType: (integer, optional) - Type of vendor. General vendor ID is 38
        + Default: 38
    + vendorTypeID: (string, required) - ID of the vendor
    + poID: (string, optional) - Purchase order ID
    + description: (string, optional) - 
    + products: (array, required) - See description for information.
    + model: (string, optional) - Options: simple, weight, weightAndPieces
        + Default: simple
    + grnMethod: (string, optional) - Options: manual
        + Default: manual
    + status: (integer, optional) - Status ID
        + Default: 1

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

# Stores - Audit [/stores/audits]
Stores audit related operations.

## Audits [POST /stores/audits]
Audits list of the organization.

+ Parameters
    + type: (integer, optional) - Type to filter the audits by a type

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

## Audit [POST /stores/audits/audit]
Audit data returned by passing the ID of the audit.

+ Parameters
    + typeID: (string, required) - TypeID to receive data on a particular audit

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

## Audit Items [POST /stores/audits/audit/items]
Items that were processed through an audit.

+ Parameters
    + id: (string, required) - Audit ID

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

## Create Audit [POST /stores/audits/audit/create]
Create audit

+ Parameters
    + type: (integer, optional) - Store type
    + typeID: (string, required) - Store id
    + name: (string, optional) - 
    + description: (string, optional) - 
    + status: (integer, optional) - Status ID
        + Default: 1

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

## Create items of an audit [POST /stores/audits/audit/items/create]
Record the items of an audit being performed

+ Parameters
    + auditID: (string, required) - Audit ID
    + barcodes: (array, required) - 

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

# Stock Transfers [/stock/stocks]
Stocks related operations.

## Stocks [POST /stock/stocks]
Stocks information of the organization.

+ Parameters
    + storeId: (string, optional) - Store ID to filter by
    + to: (string, required) - Store id of the store where the items will be transferred to.
    + method: (string, required) - The method used for transferring. Options: rfid, barcode, id
        + Default: id
    + items: (string, required) - Array of item rfid/barcode/id that will be subjected to the transfer.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "from": "46ab4658f88e312",
                "to": "46ab4658f88e8d8",
                "method": "rfid",
                "items": "{{'epc': '123123123', 'tid': 'cacacacacacac'}, {'epc': '123123123', 'tid': 'cacacacacacac'}, {'epc': '123123123', 'tid': 'cacacacacacac'}}"
            }

+ Response 200 (application/json)
    + Body

            {
                "message": "Successfully transferred the stock."
            }

## Stock by barcode [POST /stock/stocks/stock/barcode]
Stocks information of the organization.

+ Parameters
    + barcode: (string, required) - Barcode of the stock item

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

# Stock Out [/stock/stocks/out]
Stock out related operations.

## Stock-out with barcode [POST /stock/stocks/out/barcode]
Make the existing stock 0 using the barcodes

+ Parameters
    + items: (array, required) - List of barcodes to be processed on stocks to make the stock count as 0

+ Request (application/json)

+ Response 200 (application/json)
    + Body

            []

# Stock Transfers [/stock/transfers]
Stock transfers related operations.

## Transfer between stores [POST /stock/transfers/transfer]
User can transfer stock between stores.

+ Parameters
    + from: (string, required) - Store id of the store where the items are moving out of.
    + to: (string, required) - Store id of the store where the items will be transferred to.
    + txMethod: (string, required) - The method used for transferring. Options: rfid, barcode, id
        + Default: id
    + items: (string, required) - Array of item rfid/barcode/id that will be subjected to the transfer.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "from": "46ab4658f88e312",
                "to": "46ab4658f88e8d8",
                "method": "rfid",
                "items": "{{'epc': '123123123', 'tid': 'cacacacacacac'}, {'epc': '123123123', 'tid': 'cacacacacacac'}, {'epc': '123123123', 'tid': 'cacacacacacac'}}"
            }

+ Response 200 (application/json)
    + Body

            {
                "message": "Successfully transferred the stock."
            }

# Fleet - Organization [/fleet/organization]
Organization fleet related operations.

## Fleet [POST /fleet/organization]
Fleet of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "598435593c0d09cfb75abf21",
                    "oid": 102,
                    "deviceID": "213GL2015016436",
                    "vehicleName": "HY-7008"
                },
                {
                    "_id": "5984358d3c0d09cfb75abf36",
                    "oid": 102,
                    "deviceID": "213TX2015000524",
                    "vehicleName": "HY-7007"
                }
            ]

## Fleet with GPS device [POST /fleet/organization/gps]
Fleet of the organization that has GPS devices attached to them.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "598435593c0d09cfb75abf21",
                    "oid": 102,
                    "deviceID": "213GL2015016436",
                    "vehicleName": "HY-7008"
                },
                {
                    "_id": "5984358d3c0d09cfb75abf36",
                    "oid": 102,
                    "deviceID": "213TX2015000524",
                    "vehicleName": "HY-7007"
                }
            ]

# Fleet - Monitor [/fleet/monitor]
Fleet and devices related monitoring functionality.

## Monitor [POST /fleet/monitor]
Live monitoring information of the fleet of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "type": "FeatureCollection",
                    "features": [
                        {
                            "type": "Feature",
                            "geometry": {
                                "type": "Point",
                                "coordinates": [
                                    "79.8825016666666700",
                                    "6.8944916666666660"
                                ]
                            },
                            "properties": {
                                "id": "213GL2015016436",
                                "Name": "HY-7008",
                                "title": "HY-7008"
                            }
                        },
                        {
                            "type": "Feature",
                            "geometry": {
                                "type": "Point",
                                "coordinates": [
                                    "80.6069800000000000",
                                    "6.6062416666666670"
                                ]
                            },
                            "properties": {
                                "id": "213TX2015000524",
                                "Name": "HY-7007",
                                "title": "HY-7007"
                            }
                        }
                    ]
                }
            ]

# Fleet - Alarms [/fleet/alarms]
Alarms of fleet and devices.

## Alarms [POST /fleet/alarms]
Returns all alarm information for all the vehicles of the organization.

+ Parameters
    + onlyLatest: (boolean, optional) - Whether to send only the latest 50 alarm records of the fleet
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            []

# Announcements [/assets/assets]
Assets

## Create asset [POST /assets/assets/asset/create]
Create a new asset for the organization

+ Parameters
    + subType: (integer, optional) - 1: Fixed, 2: Current
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + prefix: (string, optional) - Mr., Mrs., Miss, Dr., etc. Retrieve list from API
    + telephones: (array, optional) - 
    + mobile: (string, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + website: (string, optional) - 
    + address1: (string, optional) - 
    + address2: (string, optional) - 
    + city: (string, optional) - 
    + stateID: (string, optional) - 
    + zip: (string, optional) - 
    + country: (integer, optional) - 
    + description: (string, optional) - 
    + designation: (string, optional) - 
    + categories: (array, optional) - 
    + customerSince: (date, optional) - Date as a string in the format of YYYY-mm-dd
        + Default: 2017-06-23
    + leadSourceID: (string, optional) - 
    + creditLimit: (string, optional) - 
    + creditPeriod: (string, optional) - 
    + industries: (array, optional) - 
    + marketingCampaigns: (array, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
            }

# Finance - Invoices [/finances/invoices]
Finance invoices related operations.

## Invoices list [POST /finances/invoices]
Returns all the invoices of the organization

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Invoice profile [POST /finances/invoices/invoice]
Returns the information of a invoice by passing the ID

+ Parameters
    + id: (string, required) - ID of the contact

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Invoice products [POST /finances/invoices/invoice/products]
Returns the products of a invoice by passing the ID

+ Parameters
    + id: (string, required) - ID of the sales order

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Create invoices [POST /finances/invoices/invoice/create]
Create a new invoices

+ Parameters
    + customerID: (string, optional) - Customer ID
    + name: (string, required) - Customer name
    + reference: (string, required) - 
    + salesOrderID: (string, optional) - 
    + quotationID: (string, optional) - 
    + products: (array, optional) - productID, memo, qty, unitPrice, discount, lineTotal
    + discounts: (string, optional) - 
    + creditPeriod: (string, optional) - 
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

## Payment methods [POST /finances/invoices/payment-methods]
Payment receiving methods for invoice payment collections.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

## Create payment for invoice [POST /finances/invoices/invoice/payments/payment/create]
Create a new invoices

+ Parameters
    + invoiceID: (string, required) - Invoice ID
    + bankID: (string, required) - Invoice ID
    + reference: (string, required) - 
    + total: (double, optional) - Total amount of the payment
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

# Sales - Opportunities [/sales/opportunities]
Sales opportunities related operations.

## Opportunities list [POST /sales/opportunities]
Returns all the opportunities of the organization

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Opportunity profile [POST /sales/opportunities/opportunity]
Returns the information of a opportunity by passing the ID

+ Parameters
    + id: (string, required) - ID of the contact

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Create opportunity [POST /sales/opportunities/opportunity/create]
Create a new opportunity

+ Parameters
    + customerTypeId: (string, optional) - Customer ID
    + name: (string, required) - Customer name
    + category: (string, optional) - 
    + description: (string, optional) - 
    + value: (array, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

# Sales - Quotations [/sales/quotations]
Sales quotations related operations.

## Quotations list [POST /sales/quotations]
Returns all the quotations of the organization

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Quotation profile [POST /sales/quotations/quotation]
Returns the information of a quotation by passing the ID

+ Parameters
    + id: (string, required) - ID of the contact

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Quotation products [POST /sales/quotations/quotation/products]
Returns the product of a quotation by passing the ID

+ Parameters
    + id: (string, required) - ID of the contact

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Create quotations [POST /sales/quotations/quotation/create]
Create a new sales quotation

+ Parameters
    + subType: (integer, optional) - 1: Company, 2: Individual
    + cid: (string, required) - Customer ID
    + name: (string, required) - 
    + number: (string, required) - 
    + products: (array, optional) - productID, memo, qty, unitPrice, discount, lineTotal
    + description: (string, optional) - 
    + descriptionPre: (string, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

# Sales - Orders [/sales/orders]
Sales orders related operations.

## Orders list [POST /sales/orders]
Returns all the sales orders of the organization

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

## Order profile [POST /sales/orders/order]
Returns the information of a sales order by passing the ID

+ Parameters
    + id: (string, required) - ID of the sales order

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Order products [POST /sales/orders/order/products]
Returns the products of a sales order by passing the ID

+ Parameters
    + id: (string, required) - ID of the sales order

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

## Create sales order [POST /sales/orders/order/create]
Create a new sales order

+ Parameters
    + ctype: (integer, optional) - Customer type
    + cid: (string, required) - Customer ID
    + ftype: (integer, optional) - Facilitator type
    + fid: (string, optional) - Facilitator ID
    + name: (string, optional) - 
    + number: (string, optional) - 
    + date: (string, optional) - Format Y-m-d
    + dateDue: (string, optional) - Format Y-m-d
    + description: (string, optional) - 
    + quotationID: (string, optional) - 
    + creditPeriod: (integer, optional) - 
    + products: (array, optional) - productID, memo, qty, unitPrice, discount, lineTotal
    + geoLat: (string, optional) - GPS Latitude
    + geoLon: (string, optional) - GPS Longitude
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

# Products [/products]
Products related operations.

## Products list [POST /products/products]
Returns a list of products of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "58b8dc1758e13f41fd720352",
                    "oid": 102,
                    "sku": "FXH892",
                    "barcode": "32232",
                    "name": "Mini pen drive",
                    "category": "5801b8184189dc69ad4409f6",
                    "categoryName": "Cartons",
                    "weight": null,
                    "weightUnit": null,
                    "price": 0,
                    "thresholdPrice": 0,
                    "lowestPrice": 0,
                    "purchasePrice": 0,
                    "priceCode": "-",
                    "productInfo": "This is the product description",
                    "productUrl": null,
                    "image": "",
                    "description": "This is the product description",
                    "brandName": "TOshiba",
                    "width": null,
                    "depth": null,
                    "height": null,
                    "lengthUnit": null,
                    "status": 1,
                    "creditperiod": null,
                    "cuid": 1681,
                    "uuid": 1681,
                    "created_at": "2017-03-03 02:59:35",
                    "updated_at": "2017-03-03 02:59:35"
                },
                {
                    "_id": "58be49b658e13f07784150e2",
                    "oid": 102,
                    "sku": "FXH784",
                    "barcode": "343",
                    "name": "Blurish bag",
                    "category": "5801b8184189dc69ad4409fc",
                    "categoryName": "Sample Category",
                    "weight": null,
                    "weightUnit": "Ct",
                    "cost": null,
                    "price": 2000,
                    "thresholdPrice": 1900,
                    "lowestPrice": 1850,
                    "purchasePrice": 1800,
                    "priceCode": "2323",
                    "productInfo": null,
                    "productUrl": "http://google.com",
                    "image": "",
                    "description": null,
                    "brandName": "Cabenian",
                    "width": null,
                    "depth": null,
                    "height": null,
                    "lengthUnit": "cm",
                    "status": 1,
                    "creditperiod": "12",
                    "cuid": 1652,
                    "uuid": 1652,
                    "created_at": "2017-03-07 05:48:38",
                    "updated_at": "2017-03-07 05:48:38"
                }
            ]

## Product [POST /products/products/product]
Returns the data of a product by passing the product ID.

+ Parameters
    + id: (string, required) - Product ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "580083186b0bdc05ff588792",
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "58b8dc1758e13f41fd720352",
                "oid": 102,
                "sku": "FXH892",
                "barcode": "32232",
                "name": "Mini pen drive",
                "category": "5801b8184189dc69ad4409f6",
                "categoryName": "Cartons",
                "weight": null,
                "weightUnit": null,
                "price": 0,
                "thresholdPrice": 0,
                "lowestPrice": 0,
                "purchasePrice": 0,
                "priceCode": "-",
                "productInfo": "This is the product description",
                "productUrl": null,
                "image": "",
                "description": "This is the product description",
                "brandName": "TOshiba",
                "width": null,
                "depth": null,
                "height": null,
                "lengthUnit": null,
                "status": 1,
                "creditperiod": null,
                "cuid": 1681,
                "uuid": 1681,
                "created_at": "2017-03-03 02:59:35",
                "updated_at": "2017-03-03 02:59:35"
            }

## Create product [POST /products/products/product/create]
Create a new product by posting product information.

+ Parameters
    + subType: (integer, optional) - 1:Simple, 2:Weight based pieces, 3:Weight based unit
        + Default: 1
    + sku: (string, optional) - Product SKU
    + barcode: (string, optional) - 
    + epc: (string, optional) - 
    + tid: (string, optional) - 
    + name: (string, optional) - Product name
    + category: (string, optional) - Category ID
    + packageId: (string, optional) - Package ID
    + weight: (float, optional) - 
    + weightUnit: (string, optional) - 
    + price: (float, optional) - 
    + thresholdPrice: (float, optional) - 
    + lowestPrice: (float, optional) - 
    + purchasePrice: (float, optional) - 
    + priceCode: (string, optional) - 
    + priceCurrency: (integer, optional) - Country ID of the currency
    + creditPeriod: (integer, optional) - 
    + description: (string, optional) - 
    + productInfo: (string, optional) - 
    + leadTime: (integer, optional) - Lead time in hours to receive/manufacture the product
    + productUrl: (string, optional) - 
    + brandName: (string, optional) - 
    + width: (float, optional) - 
    + depth: (float, optional) - 
    + height: (float, optional) - 
    + lengthUnit: (string, optional) - 
    + productionMaterial: (boolean, optional) - Whether this is a material used for production or not
        + Default: 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "580083186b0bdc05ff588792",
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "58b8dc1758e13f41fd720352",
                "oid": 102,
                "sku": "FXH892",
                "barcode": "32232",
                "name": "Mini pen drive",
                "category": "5801b8184189dc69ad4409f6",
                "categoryName": "Cartons",
                "weight": null,
                "weightUnit": null,
                "price": 0,
                "thresholdPrice": 0,
                "lowestPrice": 0,
                "purchasePrice": 0,
                "priceCode": "-",
                "productInfo": "This is the product description",
                "productUrl": null,
                "image": "",
                "description": "This is the product description",
                "brandName": "TOshiba",
                "width": null,
                "depth": null,
                "height": null,
                "lengthUnit": null,
                "status": 1,
                "creditperiod": null,
                "cuid": 1681,
                "uuid": 1681,
                "created_at": "2017-03-03 02:59:35",
                "updated_at": "2017-03-03 02:59:35"
            }

## Remove RFID from product (by RFID) [POST /products/product/remove-rfid]
Remove the RFID of a product by passing the EPC and TID. If the confirm parameter is sent as true, the EPC and TID will be removed. If confirm parameter is sent as false, the product matching the TID and EPC will be returned and record shall not be affected.

+ Parameters
    + tid: (string, required) - RFID TID
    + epc: (string, required) - RFID EPC
    + confirm: (boolean, optional) - If true, the RFID will be removed from the product. If false the product will be returned.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "tid": "646131657831354",
                "epc": "879113468435135",
                "confirm": false
            }

## Products update [POST /products/products/product/update]
Update a product by passing in the ID of the product along with the information that is to be updated.

+ Parameters
    + id: (string, required) - Product ID
    + sku: (string, optional) - 
    + barcode: (string, optional) - 
    + epc: (string, optional) - 
    + tid: (string, optional) - 
    + name: (string, optional) - 
    + category: (string, optional) - 
    + packageId: (string, optional) - Package ID
    + weight: (float, optional) - 
    + weightUnit: (string, optional) - 
    + price: (float, optional) - 
    + thresholdPrice: (float, optional) - 
    + lowestPrice: (float, optional) - 
    + purchasePrice: (float, optional) - 
    + priceCode: (string, optional) - 
    + priceCurrency: (integer, optional) - Country ID of the currency
    + creditPeriod: (integer, optional) - Credit period for the product in number of days
    + description: (string, optional) - 
    + productInfo: (string, optional) - 
    + leadTime: (integer, optional) - Lead time in hours to receive/manufacture the product
    + productUrl: (string, optional) - 
    + brandName: (string, optional) - 
    + width: (float, optional) - 
    + depth: (float, optional) - 
    + height: (float, optional) - 
    + lengthUnit: (string, optional) - 
    + productionMaterial: (boolean, optional) - Whether this is a material used for production or not
        + Default: 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "58b8dc1758e13f41fd720352",
                "oid": 102,
                "sku": "FXH892",
                "barcode": "32232",
                "name": "Mini pen drive",
                "category": "5801b8184189dc69ad4409f6",
                "categoryName": "Cartons",
                "weight": null,
                "weightUnit": null,
                "price": 0,
                "thresholdPrice": 0,
                "lowestPrice": 0,
                "purchasePrice": 0,
                "priceCode": "-",
                "productInfo": "This is the product description",
                "productUrl": null,
                "image": "",
                "description": "This is the product description",
                "brandName": "TOshiba",
                "width": null,
                "depth": null,
                "height": null,
                "lengthUnit": null,
                "status": 1,
                "creditperiod": null,
                "cuid": 1681,
                "uuid": 1681,
                "created_at": "2017-03-03 02:59:35",
                "updated_at": "2017-03-03 02:59:35"
            }

# Product Packages [/products/packages]
Product Packages related operations.

## Product packages list [POST /products/packages]
Returns a list of product packages of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "58b8dc1758e13f41fd720352",
                    "oid": 102,
                    "sku": "FXH892",
                    "barcode": "32232",
                    "name": "Mini pen drive",
                    "category": "5801b8184189dc69ad4409f6",
                    "categoryName": "Cartons",
                    "weight": null,
                    "weightUnit": null,
                    "price": 0,
                    "thresholdPrice": 0,
                    "lowestPrice": 0,
                    "purchasePrice": 0,
                    "priceCode": "-",
                    "productInfo": "This is the product description",
                    "productUrl": null,
                    "image": "",
                    "description": "This is the product description",
                    "brandName": "TOshiba",
                    "width": null,
                    "depth": null,
                    "height": null,
                    "lengthUnit": null,
                    "status": 1,
                    "creditperiod": null,
                    "cuid": 1681,
                    "uuid": 1681,
                    "created_at": "2017-03-03 02:59:35",
                    "updated_at": "2017-03-03 02:59:35"
                },
                {
                    "_id": "58be49b658e13f07784150e2",
                    "oid": 102,
                    "sku": "FXH784",
                    "barcode": "343",
                    "name": "Blurish bag",
                    "category": "5801b8184189dc69ad4409fc",
                    "categoryName": "Sample Category",
                    "weight": null,
                    "weightUnit": "Ct",
                    "cost": null,
                    "price": 2000,
                    "thresholdPrice": 1900,
                    "lowestPrice": 1850,
                    "purchasePrice": 1800,
                    "priceCode": "2323",
                    "productInfo": null,
                    "productUrl": "http://google.com",
                    "image": "",
                    "description": null,
                    "brandName": "Cabenian",
                    "width": null,
                    "depth": null,
                    "height": null,
                    "lengthUnit": "cm",
                    "status": 1,
                    "creditperiod": "12",
                    "cuid": 1652,
                    "uuid": 1652,
                    "created_at": "2017-03-07 05:48:38",
                    "updated_at": "2017-03-07 05:48:38"
                }
            ]

## Product package [POST /products/packages/package]
Returns the data of a product package.

+ Parameters
    + id: (string, required) - Package ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            []

## Create product package [POST /products/packages/package/create]
Create a product package and returns its data.

+ Parameters
    + id: (string, required) - Package ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            []

## Update product package [POST /products/packages/package/update]
Update the existing info of a product package and returns its new data.

+ Parameters
    + id: (string, required) - Package ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            []

# RFID [/rfid]
RFID related operations.

## Assign RFID to product [POST /rfid/stores]
Returns the full list of warehouses

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 17,
                "typeId": "46ab4658f88e8d8"
            }

+ Response 200 (application/json)
    + Body

            {
                "id": 10,
                "username": "foo"
            }

## Product lookup by RFID [POST /rfid/stores]
Returns the full list of warehouses

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "tid": 9223372036854775807,
                "epc": "46ab4658f88e8d8"
            }

+ Response 200 (application/json)
    + Body

            {
                "id": 10,
                "username": "foo"
            }

# CRM - Customers [/orders]
Production oders related operations.

## Orders [POST /orders]
Returns the full list of production orders

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

## Materials of the production order [POST /orders/order/material]
Returns the full list of required materials and their quantities for a provided production order

+ Parameters
    + id: (string, required) - Production order ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "59bdd35301aca6bd4e2df072"
            }

# Material for Production [/production/materials]
Production material related operations.

## Material list [POST /production/materials]
Returns a list of materials used for production of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "58b8dc1758e13f41fd720352",
                    "oid": 102,
                    "sku": "FXH892",
                    "barcode": "32232",
                    "name": "Mini pen drive",
                    "category": "5801b8184189dc69ad4409f6",
                    "categoryName": "Cartons",
                    "weight": null,
                    "weightUnit": null,
                    "price": 0,
                    "thresholdPrice": 0,
                    "lowestPrice": 0,
                    "purchasePrice": 0,
                    "priceCode": "-",
                    "productInfo": "This is the product description",
                    "productUrl": null,
                    "image": "",
                    "description": "This is the product description",
                    "brandName": "TOshiba",
                    "width": null,
                    "depth": null,
                    "height": null,
                    "lengthUnit": null,
                    "status": 1,
                    "creditperiod": null,
                    "cuid": 1681,
                    "uuid": 1681,
                    "created_at": "2017-03-03 02:59:35",
                    "updated_at": "2017-03-03 02:59:35"
                },
                {
                    "_id": "58be49b658e13f07784150e2",
                    "oid": 102,
                    "sku": "FXH784",
                    "barcode": "343",
                    "name": "Blurish bag",
                    "category": "5801b8184189dc69ad4409fc",
                    "categoryName": "Sample Category",
                    "weight": null,
                    "weightUnit": "Ct",
                    "cost": null,
                    "price": 2000,
                    "thresholdPrice": 1900,
                    "lowestPrice": 1850,
                    "purchasePrice": 1800,
                    "priceCode": "2323",
                    "productInfo": null,
                    "productUrl": "http://google.com",
                    "image": "",
                    "description": null,
                    "brandName": "Cabenian",
                    "width": null,
                    "depth": null,
                    "height": null,
                    "lengthUnit": "cm",
                    "status": 1,
                    "creditperiod": "12",
                    "cuid": 1652,
                    "uuid": 1652,
                    "created_at": "2017-03-07 05:48:38",
                    "updated_at": "2017-03-07 05:48:38"
                }
            ]

## Material [POST /production/materials/material]
Returns the data of a material by passing the ID.

+ Parameters
    + id: (string, required) - Material/product ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "580083186b0bdc05ff588792",
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "58b8dc1758e13f41fd720352",
                "oid": 102,
                "sku": "FXH892",
                "barcode": "32232",
                "name": "Mini pen drive",
                "category": "5801b8184189dc69ad4409f6",
                "categoryName": "Cartons",
                "weight": null,
                "weightUnit": null,
                "price": 0,
                "thresholdPrice": 0,
                "lowestPrice": 0,
                "purchasePrice": 0,
                "priceCode": "-",
                "productInfo": "This is the product description",
                "productUrl": null,
                "image": "",
                "description": "This is the product description",
                "brandName": "TOshiba",
                "width": null,
                "depth": null,
                "height": null,
                "lengthUnit": null,
                "status": 1,
                "creditperiod": null,
                "cuid": 1681,
                "uuid": 1681,
                "created_at": "2017-03-03 02:59:35",
                "updated_at": "2017-03-03 02:59:35"
            }

## Create material [POST /production/materials/material/create]
Create a new material by posting material information.

+ Parameters
    + subType: (integer, optional) - 1:Simple, 2:Weight based pieces, 3:Weight based unit
        + Default: 1
    + sku: (string, optional) - Material SKU
    + barcode: (string, optional) - 
    + epc: (string, optional) - 
    + tid: (string, optional) - 
    + name: (string, optional) - Material name
    + commonName: (string, optional) - Common name known by
    + category: (string, optional) - Category ID
    + packageId: (string, optional) - Package ID
    + weight: (float, optional) - 
    + weightUnit: (string, optional) - 
    + description: (string, optional) - 
    + handlingInstructions: (string, optional) - 
    + warnings: (string, optional) - 
    + leadTime: (integer, optional) - Lead time in hours to receive/manufacture the material
    + productUrl: (string, optional) - 
    + brandName: (string, optional) - 
    + width: (float, optional) - 
    + depth: (float, optional) - 
    + height: (float, optional) - 
    + lengthUnit: (string, optional) - 
    + productionMaterial: (boolean, optional) - Whether this is a material used for production or not
        + Default: 1
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "580083186b0bdc05ff588792",
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "58b8dc1758e13f41fd720352",
                "oid": 102,
                "sku": "FXH892",
                "barcode": "32232",
                "name": "Mini pen drive",
                "category": "5801b8184189dc69ad4409f6",
                "categoryName": "Cartons",
                "weight": null,
                "weightUnit": null,
                "price": 0,
                "thresholdPrice": 0,
                "lowestPrice": 0,
                "purchasePrice": 0,
                "priceCode": "-",
                "productInfo": "This is the product description",
                "productUrl": null,
                "image": "",
                "description": "This is the product description",
                "brandName": "TOshiba",
                "width": null,
                "depth": null,
                "height": null,
                "lengthUnit": null,
                "status": 1,
                "creditperiod": null,
                "cuid": 1681,
                "uuid": 1681,
                "created_at": "2017-03-03 02:59:35",
                "updated_at": "2017-03-03 02:59:35"
            }

## Material update [POST /production/materials/product/update]
Update a material by passing in the ID of the material along with the information that is to be updated.

+ Parameters
    + id: (string, required) - Material ID
    + sku: (string, optional) - 
    + barcode: (string, optional) - 
    + epc: (string, optional) - 
    + tid: (string, optional) - 
    + name: (string, optional) - 
    + commonName: (string, optional) - Common name known by
    + category: (string, optional) - 
    + packageId: (string, optional) - Package ID
    + weight: (float, optional) - 
    + weightUnit: (string, optional) - 
    + description: (string, optional) - 
    + handlingInstructions: (string, optional) - 
    + warnings: (string, optional) - 
    + leadTime: (integer, optional) - Lead time in hours to receive/manufacture the product
    + productUrl: (string, optional) - 
    + brandName: (string, optional) - 
    + width: (float, optional) - 
    + depth: (float, optional) - 
    + height: (float, optional) - 
    + lengthUnit: (string, optional) - 
    + productionMaterial: (boolean, optional) - Whether this is a material used for production or not
        + Default: 1
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "58b8dc1758e13f41fd720352",
                "oid": 102,
                "sku": "FXH892",
                "barcode": "32232",
                "name": "Mini pen drive",
                "category": "5801b8184189dc69ad4409f6",
                "categoryName": "Cartons",
                "weight": null,
                "weightUnit": null,
                "price": 0,
                "thresholdPrice": 0,
                "lowestPrice": 0,
                "purchasePrice": 0,
                "priceCode": "-",
                "productInfo": "This is the product description",
                "productUrl": null,
                "image": "",
                "description": "This is the product description",
                "brandName": "TOshiba",
                "width": null,
                "depth": null,
                "height": null,
                "lengthUnit": null,
                "status": 1,
                "creditperiod": null,
                "cuid": 1681,
                "uuid": 1681,
                "created_at": "2017-03-03 02:59:35",
                "updated_at": "2017-03-03 02:59:35"
            }

# Purchase Orders [/purchasing/orders]
Purchase order related operations.

## Purchase order list [POST /purchasing/orders]
Returns a list of purchase orders of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

## Purchase order [POST /purchasing/orders/order]
Returns a purchase orders of the organization by it's ID.

+ Parameters
    + id: (string, required) - ID of the purchase order

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "1646315684613668"
            }

## Create purchase order [POST /purchasing/orders/order/create]
Create a new purchase orders.

+ Parameters
    + sendImage: (boolean, optional) - Whether a publicly accessible URL needed or not. Link is valid only for 1 Hour.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

# Vendors [/purchasing/vendors]
Vendor related operations.

## Vendors [POST /purchasing/vendors]
Vendors of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "596b467e4189dce08e1170a2",
                    "name": "Sample vendor one",
                    "email": "sv1@flatorb.com",
                    "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
                    "oid": 102,
                    "addresses": {
                        "main": {
                            "address1": "123 Some Street",
                            "address2": "",
                            "city": "",
                            "state": null,
                            "stateID": "",
                            "zip": "32165",
                            "country": null,
                            "countryID": null,
                            "description": null,
                            "status": 1,
                            "cuid": 1,
                            "uuid": 1,
                            "created_at": "2017-07-16 10:57:02",
                            "updated_at": "2017-07-16 10:57:02"
                        }
                    },
                    "telephones": [
                        "1234567890"
                    ],
                    "mobiles": [
                        "7894561233"
                    ],
                    "status": 1,
                    "statusName": "Active",
                    "cuid": 1,
                    "cuName": "Anushan",
                    "uuid": 1,
                    "uuName": "Anushan",
                    "updated_at": "2017-07-16 10:57:02",
                    "created_at": "2017-07-16 10:57:02"
                }
            ]

## Vendors [POST /purchasing/vendors/vendor/create]
Create vendors of the organization.

+ Parameters
    + name: (string, required) - 
        + Default: 1
    + email: (string, optional) - 
        + Default: 1
    + website: (string, optional) - 
        + Default: 1
    + mobile: (string, optional) - 
        + Default: 1
    + description: (string, optional) - 
        + Default: 1

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "580083186b0bdc05ff588792",
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "596b467e4189dce08e1170a2",
                    "name": "Sample vendor one",
                    "email": "sv1@flatorb.com",
                    "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
                    "oid": 102,
                    "addresses": {
                        "main": {
                            "address1": "123 Some Street",
                            "address2": "",
                            "city": "",
                            "state": null,
                            "stateID": "",
                            "zip": "32165",
                            "country": null,
                            "countryID": null,
                            "description": null,
                            "status": 1,
                            "cuid": 1,
                            "uuid": 1,
                            "created_at": "2017-07-16 10:57:02",
                            "updated_at": "2017-07-16 10:57:02"
                        }
                    },
                    "telephones": [
                        "1234567890"
                    ],
                    "mobiles": [
                        "7894561233"
                    ],
                    "status": 1,
                    "statusName": "Active",
                    "cuid": 1,
                    "cuName": "Anushan",
                    "uuid": 1,
                    "uuName": "Anushan",
                    "updated_at": "2017-07-16 10:57:02",
                    "created_at": "2017-07-16 10:57:02"
                }
            ]

## Vendors [POST /purchasing/vendors/vendor/update]
Update vendors of the organization.

+ Parameters
    + name: (string, required) - 
        + Default: 1
    + email: (string, optional) - 
        + Default: 1
    + website: (string, optional) - 
        + Default: 1
    + mobile: (string, optional) - 
        + Default: 1
    + description: (string, optional) - 
        + Default: 1

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "580083186b0bdc05ff588792",
                "sendImage": false
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "596b467e4189dce08e1170a2",
                    "name": "Sample vendor one",
                    "email": "sv1@flatorb.com",
                    "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim.",
                    "oid": 102,
                    "addresses": {
                        "main": {
                            "address1": "123 Some Street",
                            "address2": "",
                            "city": "",
                            "state": null,
                            "stateID": "",
                            "zip": "32165",
                            "country": null,
                            "countryID": null,
                            "description": null,
                            "status": 1,
                            "cuid": 1,
                            "uuid": 1,
                            "created_at": "2017-07-16 10:57:02",
                            "updated_at": "2017-07-16 10:57:02"
                        }
                    },
                    "telephones": [
                        "1234567890"
                    ],
                    "mobiles": [
                        "7894561233"
                    ],
                    "status": 1,
                    "statusName": "Active",
                    "cuid": 1,
                    "cuName": "Anushan",
                    "uuid": 1,
                    "uuName": "Anushan",
                    "updated_at": "2017-07-16 10:57:02",
                    "created_at": "2017-07-16 10:57:02"
                }
            ]

# Marketing campaigns [/marketing/campaigns]
Marketing campaigns related operations.

## List of marketing campaigns [POST /marketing/campaigns]
Returns the full list of marketing campaigns of the organization.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "580494806b0bdc02f42265a2",
                    "oid": 102,
                    "category": "5804912b6b0bdc0212189812",
                    "categoryName": "Test campaign",
                    "name": "New marketing campaign",
                    "assignTo": "",
                    "location": "Colombo",
                    "description": "",
                    "budget": "23123",
                    "startDate": "2016-10-17",
                    "endDate": "2016-10-17",
                    "status": 1,
                    "cuid": 6,
                    "uuid": 6,
                    "created_at": "2016-10-17 09:06:07",
                    "updated_at": "2016-10-17 09:06:07"
                },
                {
                    "_id": "58117e1458e13f768426e152",
                    "oid": 102,
                    "category": "5801b8184189dc69ad4409d3",
                    "categoryName": "marketing campaign",
                    "name": "Promotional campaign",
                    "assignTo": "5805e3ac6b0bdc09d366df82",
                    "location": "Pamankada",
                    "description": "This is a promotional campaign",
                    "budget": "100000",
                    "startDate": "2016-10-27",
                    "endDate": "2016-10-30",
                    "status": 1,
                    "cuid": 1685,
                    "uuid": 1685,
                    "created_at": "2016-10-27 04:09:56",
                    "updated_at": "2016-10-27 04:09:56"
                },
                {
                    "_id": "5816cd3f58e13f0b602a8ac2",
                    "oid": 102,
                    "category": "5801b8184189dc69ad440a22",
                    "categoryName": "Annual category",
                    "name": "Free give away",
                    "assignTo": "5805e3ac6b0bdc09d366df82",
                    "location": "Galleface",
                    "description": "Yearly giveaways ",
                    "budget": "100000",
                    "startDate": "2016-10-31",
                    "endDate": "2016-11-04",
                    "status": 1,
                    "cuid": 1685,
                    "uuid": 1685,
                    "created_at": "2016-10-31 04:49:03",
                    "updated_at": "2016-10-31 04:49:03"
                }
            ]

## Campaign profile (single) [POST /marketing/campaigns/campaign]
Returns the information of a campaign profile retrieved by the ID

+ Parameters
    + id: (string, required) - Campaign ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5810752a6b0bdc094041d6e2",
                "oid": 102,
                "source": "Email"
            }

## Campaigns by IDs (multiple) [POST /marketing/campaigns/campaigns]
Returns the information of campaigns by passing in the Ids

+ Parameters
    + ids: (array, required) - Campaign IDs as an array or a comma separated list
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "ids": "546813a68bc6, 1464a135be6, 6846fe65"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "5810752a6b0bdc094041d6e2",
                    "oid": 102,
                    "source": "Email"
                },
                {
                    "_id": "581ab09f58e13f433041dcc2",
                    "oid": 102,
                    "source": "Caller"
                }
            ]

# Events [/events/events]
Events

## Events [POST /events/events]
Returns the full list of events

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

## Events profile [POST /events/events/event]
Returns the information of an event

+ Parameters
    + eventId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "eventId": "546813a68bc6"
            }

## Create event [POST /events/events/event/create]
Create a new event for the organization

+ Parameters
    + type: (string, required) - 42: Belongs to events
        + Default: 
    + typeid: (string, required) - ID of the above type if applicable
        + Default: 
    + eventType: (integer, required) - 1: Public, 2: Private
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + category: (string, optional) - 
    + address: (string, optional) - 
    + latitude: (array, optional) - 
    + longitude: (string, optional) - 
    + date: (date, optional) - 
    + startTime: (timestamp, optional) - 
    + endTime: (timestamp, optional) - 
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "eventId": "546813a68bc6"
            }

## Edit event [POST /events/events/event/update]
Edit/update an event information.

+ Parameters
    + id: (string, required) - Evnet ID
    + eventType: (integer, required) - 1: Public, 2: Private
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + category: (string, optional) - 
    + address: (string, optional) - 
    + latitude: (array, optional) - 
    + longitude: (string, optional) - 
    + date: (date, optional) - 
    + startTime: (timestamp, optional) - 
    + endTime: (timestamp, optional) - 
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

# Announcements [/communications/announcements]
Announcements

## Announcements [POST /communications/announcements]
Returns the full list of Announcements

## Announcement profile [POST /communications/announcements/announcement]
Returns the information of an Announcement

+ Parameters
    + announcementId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "announcementId": "546813a68bc6"
            }

## Create announcement [POST /communications/announcements/announcement/create]
Create a new announcement for the organization

+ Parameters
    + type: (string, required) - 43: Belongs to announcement
        + Default: 
    + typeid: (string, required) - ID of the above type if applicable
        + Default: 
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + date: (string, optional) - 
    + location: (string, optional) - 
    + featured: (boolean, optional) - 
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "announcementId": "546813a68bc6"
            }

## Edit announcement [POST /communications/announcements/announcement/update]
Edit/update an announcement information.

+ Parameters
    + id: (string, required) - Evnet ID
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + date: (string, optional) - 
    + location: (string, optional) - 
    + featured: (boolean, optional) - 
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

# Events [/fundraising/fundraisers]
Fundraising

## Fundraising [POST /fundraising/fundraisers]
Returns the full list of fundraisers

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

## Fundraising profile [POST /fundraising/fundraisers/fundraiser]
Returns the information of fundraiser

+ Parameters
    + fundraiserId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "fundraiserId": "546813a68bc6"
            }

## Create a fundraiser [POST /fundraising/fundraisers/fundraiser/create]
Create a new fundraiser for the organization

+ Parameters
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + target: (string, optional) - 
    + location: (string, optional) - 
    + startDate: (date, optional) - 
    + endDate: (date, optional) - 
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "fundraiserId": "546813a68bc6"
            }

## Edit fundraiser [POST /fundraising/fundraisers/fundraiser/update]
Edit/update a fundraiser information.

+ Parameters
    + id: (string, required) - Evnet ID
    + name: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + target: (string, optional) - 
    + location: (string, optional) - 
    + startDate: (date, optional) - 
    + endDate: (date, optional) - 
    + description: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

# Fundraising - Fundraiser [/fundraising/fundraisers]
Fundraising related operations.

## Create a donation [POST /fundraising/fundraisers/fundraiser/create]
Create a new donation for the fundraiser

+ Parameters
    + type: (string, required) - 44: Belongs to fundraiser
        + Default: 
    + typeid: (string, required) - ID of the above type if applicable
        + Default: 
    + customerId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 
    + amount: (string, optional) - 
    + paymentMethod: (string, optional) - 
    + description: (date, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "donationId": "546813a68bc6"
            }

## Fundraiser donations [POST /fundraising/fundraisers/fundraiser/donations]
Returns the donations that are associated with the fundraiser

+ Parameters
    + fundraiserId: (string, required) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "fundraiserId": "546813a68bc6"
            }

# MAINTENANCE [/maintenances]
Maintenance related data and information for every place where maintenance records are applicable.

## Maintenance list of a typeId [POST /maintenances/maintenance]
Returns the full list of maintenances for a defined item

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 17,
                "typeId": "46ab4658f88e8d8"
            }

+ Response 200 (application/json)
    + Body

            {
                "id": 10,
                "username": "foo"
            }

## Create new maintenance record [POST /maintenances/save]
Allows the user to create a maintenance record for an item.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 17,
                "typeId": "46ab4658f88e8d8"
            }

+ Response 200 (application/json)
    + Body

            {
                "id": 10,
                "username": "foo"
            }

## Save "before" part for a before & after maintenance record [POST /maintenances/saveBefore]
Allows the user to create the before part fo a maintenance record for an item for the Before & After type of a maintenance record.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 17,
                "typeId": "46ab4658f88e8d8",
                "name": "Monthly wash for September",
                "0": "startLon"
            }

+ Response 200 (application/json)
    + Body

            {
                "id": 10,
                "username": "foo"
            }

## Save "after" part for a before & after maintenance record [POST /maintenances/saveAfter]
Allows the user to create the "after" part fo a maintenance record for an item for the Before & After type of a maintenance record.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 17,
                "typeId": "46ab4658f88e8d8"
            }

+ Response 200 (application/json)
    + Body

            {
                "id": 10,
                "username": "foo"
            }

# Announcements [/maintenances]
Maintenance

## Create maintenance record [POST /maintenances/maintenance/create]
Create a new maintenance record

+ Parameters
    + type: (integer, required) - 
    + typeID: (string, required) - 
        + Default: 
    + typeName: (string, required) - 
        + Default: 
    + name: (string, required) - W
        + Default: 
    + description: (string, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            []

# Uploads of Modules [/files]
Module file uploads related operations.

## Uploads [POST /files/uploads]
Returns the uploaded files of the organization. Results can be filtered by passing in the type and the typeid.

+ Parameters
    + type: (integer, optional) - Type
        + Default: 
    + typeid: (string, optional) - Type ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5800a64e6b0bdc07300ee8e3",
                "oid": 102,
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743",
                "filename": "1476437576-7xgp4WI3CirnMC9s2H9k.jpeg",
                "filesize": 4.7,
                "bucket": "s3",
                "status": 1,
                "cuid": 6,
                "uuid": 6,
                "created_at": "2016-10-14 09:32:56",
                "updated_at": "2016-10-14 09:32:56",
                "imgP": "https:\/\/fxhellouat.s3.amazonaws.com\/data\/102\/customer\/5800a25a6b0bdc06a814c743\/1476437576-7xgp4WI3CirnMC9s2H9k.jpeg?X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJUVQVA4VO7WZAOVQ%2F20170629%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20170629T043224Z&X-Amz-SignedHeaders=host&X-Amz-Expires=604200&X-Amz-Signature=59c48f60a0ac229e977c78c42758b7384256574f9ad5cce664d2781f7be256c1",
                "imgExpire": 1499240742
            }

## Upload profile image [POST /files/upload/profile]
Returns the uploaded files of the organization. Results can be filtered by passing in the type and the typeid.

+ Parameters
    + type: (integer, required) - Type
        + Default: 
    + typeid: (string, required) - Type ID
        + Default: 
    + file: (file, required) - Image file in format JPG, JPEG, GIF, PNG
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5800a64e6b0bdc07300ee8e3",
                "oid": 102,
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743",
                "filename": "1476437576-7xgp4WI3CirnMC9s2H9k.jpeg",
                "filesize": 4.7,
                "bucket": "s3",
                "status": 1,
                "cuid": 6,
                "uuid": 6,
                "created_at": "2016-10-14 09:32:56",
                "updated_at": "2016-10-14 09:32:56",
                "imgP": "https:\/\/fxhellouat.s3.amazonaws.com\/data\/102\/customer\/5800a25a6b0bdc06a814c743\/1476437576-7xgp4WI3CirnMC9s2H9k.jpeg?X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJUVQVA4VO7WZAOVQ%2F20170629%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20170629T043224Z&X-Amz-SignedHeaders=host&X-Amz-Expires=604200&X-Amz-Signature=59c48f60a0ac229e977c78c42758b7384256574f9ad5cce664d2781f7be256c1",
                "imgExpire": 1499240742
            }

## Upload attachment [POST /files/upload/attach]
Upload a single attachment to an item by providing its type and typeId

+ Parameters
    + type: (integer, required) - Type
    + typeid: (string, required) - Type ID
    + attachment: (file, required) - Attachment with acceptable file extention
    + isCertificate: (boolean, optional) - Is this a certificate
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5800a64e6b0bdc07300ee8e3",
                "oid": 102,
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743",
                "filename": "1476437576-7xgp4WI3CirnMC9s2H9k.jpeg",
                "filesize": 4.7,
                "bucket": "s3",
                "status": 1,
                "cuid": 6,
                "uuid": 6,
                "created_at": "2016-10-14 09:32:56",
                "updated_at": "2016-10-14 09:32:56",
                "imgP": "https:\/\/fxhellouat.s3.amazonaws.com\/data\/102\/customer\/5800a25a6b0bdc06a814c743\/1476437576-7xgp4WI3CirnMC9s2H9k.jpeg?X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJUVQVA4VO7WZAOVQ%2F20170629%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20170629T043224Z&X-Amz-SignedHeaders=host&X-Amz-Expires=604200&X-Amz-Signature=59c48f60a0ac229e977c78c42758b7384256574f9ad5cce664d2781f7be256c1",
                "imgExpire": 1499240742
            }

## Upload attachments - multiple [POST /files/upload/attach-multiple]
Upload multiple attachments to an item by providing its type and typeId

+ Parameters
    + type: (integer, required) - Type
        + Default: 
    + typeid: (string, required) - Type ID
        + Default: 
    + attachments: (array, required) - Attachment with acceptable file extention
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5800a64e6b0bdc07300ee8e3",
                "oid": 102,
                "type": 3,
                "typeid": "5800a25a6b0bdc06a814c743",
                "filename": "1476437576-7xgp4WI3CirnMC9s2H9k.jpeg",
                "filesize": 4.7,
                "bucket": "s3",
                "status": 1,
                "cuid": 6,
                "uuid": 6,
                "created_at": "2016-10-14 09:32:56",
                "updated_at": "2016-10-14 09:32:56",
                "imgP": "https:\/\/fxhellouat.s3.amazonaws.com\/data\/102\/customer\/5800a25a6b0bdc06a814c743\/1476437576-7xgp4WI3CirnMC9s2H9k.jpeg?X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAJUVQVA4VO7WZAOVQ%2F20170629%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20170629T043224Z&X-Amz-SignedHeaders=host&X-Amz-Expires=604200&X-Amz-Signature=59c48f60a0ac229e977c78c42758b7384256574f9ad5cce664d2781f7be256c1",
                "imgExpire": 1499240742
            }

# SYSTEM [/system]
Maintenance related data and information for every place where maintenance records are applicable.

## List of types [POST /system/types]
Returns the full list of "types" of the system.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 17,
                "typeId": "46ab4658f88e8d8"
            }

+ Response 200 (application/json)
    + Body

            {
                "1": "User",
                "2": "Organization",
                "3": "Customer",
                "4": "Contact",
                "5": "Products",
                "6": "HR",
                "7": "Warehouse",
                "8": "Distribution Center"
            }

# Status [/system/statuses]
Statuses related operations.

## List of statuses [POST /system/statuses]
Returns the full list of "statuses" of the system. Type specific statuses can be retrieved by passing the type parameter.

+ Parameters
    + type: (integer, optional) - Type of the status

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 17
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": 1,
                    "oid": 0,
                    "type": 0,
                    "name": "Active",
                    "status": 1,
                    "cuid": 0,
                    "uuid": 0,
                    "created_at": null,
                    "updated_at": null
                },
                {
                    "id": 2,
                    "oid": 0,
                    "type": 0,
                    "name": "Inactive",
                    "status": 1,
                    "cuid": 0,
                    "uuid": 0,
                    "created_at": null,
                    "updated_at": null
                },
                {
                    "id": 7,
                    "oid": 0,
                    "type": 0,
                    "name": "Pending",
                    "status": 1,
                    "cuid": 0,
                    "uuid": 0,
                    "created_at": null,
                    "updated_at": null
                }
            ]

# React [/communications/announcements]
Reaction related operations for types

## Reacts [POST /communications/announcements/react]
Returns the reaction to the relevant event

+ Parameters
    + oid: (string, required) - Organization ID of the app or event
    + type: (integer, required) - 
    + typeID: (string, required) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "oid": "546813a68bc6"
            }

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 42
            }

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "typeID": "546813a68bc6"
            }

## React create [POST /communications/announcements/react/create]


+ Parameters
    + oid: (integer, required) - organization ID
    + type: (integer, required) - E.g. Event = 42
        + Default: 
    + typeID: (string, required) - ID of the relevant type
    + userID: (integer, required) - 
    + reaction: (string, required) - Going, May be, Nop

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "reactId": "546813a68bc6"
            }

## React update [POST /communications/announcements/react/update]


+ Parameters
    + id: (string, required) - reaction ID
    + reaction: (string, required) - Going, May be, Nop

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

# Industries [/system/industries]
Industries related operations.

## Industries [POST /system/industries]
Returns the full list of industries, provided by the system as well as owned by the organization

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "5810752a6b0bdc094041d6e2",
                    "oid": 102,
                    "source": "Email"
                },
                {
                    "_id": "581ab09f58e13f433041dcc2",
                    "oid": 102,
                    "source": "Caller"
                }
            ]

## Industry (single) [POST /system/industries/industry]
Returns the information of a industry

+ Parameters
    + id: (string, required) - Industry ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "5810752a6b0bdc094041d6e2",
                "oid": 102,
                "source": "Email"
            }

## Industries by IDs (multiple) [POST /system/industries/industries]
Returns the information of industries by passing in the Ids

+ Parameters
    + ids: (array, required) - Lead source IDs an an array or a comma seperated list
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "ids": "546813a68bc6, 1464a135be6, 6846fe65"
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "5810752a6b0bdc094041d6e2",
                    "oid": 102,
                    "source": "Email"
                },
                {
                    "_id": "581ab09f58e13f433041dcc2",
                    "oid": 102,
                    "source": "Caller"
                }
            ]

## Create a new industry [POST /system/industries/industry/create]
Create a new industry for the organization

+ Parameters
    + description: (string, required) - Name of the industry
        + Default: 
    + isic_r4: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "description": "Expo XYZ",
                "isic_r4": "1"
            }

## Update an existing industry [POST /system/industries/industry/update]
Update an existing industry of the organization by passing in the ID of the industry

+ Parameters
    + id: (string, required) - ID of industry to edit
        + Default: 
    + description: (string, optional) - Name of the industry
        + Default: 
    + isic_r4: (string, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "5810752a6b0bdc094041d6e2",
                "description": "Expo XYZ",
                "isic_r4": 1
            }

# Mails [/system/mails]
Mails related operations.

## Send mail [POST /system/mails/mail/create]
Sending an email

+ Parameters
    + type: (integer, required) - Sender type
    + typeid: (string, required) - ID of the relevant sender
    + typeName: (string, required) - Name of the relevant sender
    + to: (string, required) - Recipient email
    + from: (string, required) - Sender email
    + subject: (string, optional) - Subject
    + message: (string, optional) - Message

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "546813a68bc6"
            }

# Notes [/general/notes]
Notes related operations.

## Notes [POST /general/notes]
Returns the full list of notes

+ Parameters
    + type: (integer, optional) - Type of the notes if filtration is required
    + typeid: (string, optional) - Type ID of the notes if filtration is required

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "type": 3
            }

+ Response 200 (application/json)
    + Body

            [
                {
                    "_id": "59631ae34189dc7ef8349672",
                    "type": 3,
                    "typeid": "58005d3d6b0bdc03e27274d4",
                    "subType": null,
                    "title": "This is a sample note one",
                    "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu.",
                    "parent": null,
                    "priority": null,
                    "oid": 102,
                    "isTask": false,
                    "isNote": true,
                    "dueDate": null,
                    "assigneeType": null,
                    "status": 1,
                    "statusName": "Active",
                    "cuid": 1,
                    "cuName": "John",
                    "uuid": 1,
                    "uuName": "John",
                    "updated_at": "2017-07-10 06:12:51",
                    "created_at": "2017-07-10 06:12:51"
                },
                {
                    "_id": "59631cfc4189dc10a47fede2",
                    "type": 3,
                    "typeid": "58005d3d6b0bdc03e27274d4",
                    "subType": null,
                    "title": "This is a sample note two",
                    "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu.",
                    "parent": null,
                    "priority": null,
                    "oid": 102,
                    "isTask": false,
                    "isNote": true,
                    "dueDate": null,
                    "assigneeType": null,
                    "status": 1,
                    "statusName": "Active",
                    "cuid": 1,
                    "cuName": "John",
                    "uuid": 1,
                    "uuName": "John",
                    "updated_at": "2017-07-10 06:21:48",
                    "created_at": "2017-07-10 06:21:48"
                }
            ]

## Note [POST /general/notes/note]
Returns the note information

+ Parameters
    + id: (integer, required) - Note ID

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "59631ae34189dc7ef8349672"
            }

+ Response 200 (application/json)
    + Body

            {
                "_id": "59631ae34189dc7ef8349672",
                "type": 3,
                "typeid": "58005d3d6b0bdc03e27274d4",
                "subType": null,
                "title": "This is a sample note one",
                "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu.",
                "parent": null,
                "priority": null,
                "oid": 102,
                "isTask": false,
                "isNote": true,
                "dueDate": null,
                "assigneeType": null,
                "status": 1,
                "statusName": "Active",
                "cuid": 1,
                "cuName": "John",
                "uuid": 1,
                "uuName": "John",
                "updated_at": "2017-07-10 06:12:51",
                "created_at": "2017-07-10 06:12:51"
            }

## Create a note [POST /general/notes/note/create]
Create a new note

+ Parameters
    + type: (integer, required) - Type
    + typeid: (string, required) - Type ID
    + subType: (integer, optional) - Sub type
    + title: (string, optional) - Title for the note
    + comment: (string, required) - Comment body and description content
    + parent: (string, optional) - ID of the parent note/comment
    + priority: (string, optional) - Options: Highest, High, Normal, Low, Lowest
    + isTask: (bollean, optional) - Is this a task
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            {
                "_id": "59631ae34189dc7ef8349672",
                "type": 3,
                "typeid": "58005d3d6b0bdc03e27274d4",
                "subType": null,
                "title": "This is a sample note one",
                "comment": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu.",
                "parent": null,
                "priority": null,
                "oid": 102,
                "isTask": false,
                "isNote": true,
                "dueDate": null,
                "assigneeType": null,
                "status": 1,
                "statusName": "Active",
                "cuid": 1,
                "cuName": "John",
                "uuid": 1,
                "uuName": "John",
                "updated_at": "2017-07-10 06:12:51",
                "created_at": "2017-07-10 06:12:51"
            }

# Address [/general/addresses]
Addresses related operations.

## Countries [POST /general/addresses/countries]
Returns the list of countries.

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            [
                {
                    "id": 1,
                    "country": "Andorra",
                    "code": "AD",
                    "currency_code": "EUR"
                },
                {
                    "id": 2,
                    "country": "United Arab Emirates",
                    "code": "AE",
                    "currency_code": "AED"
                },
                {
                    "id": 3,
                    "country": "Afghanistan",
                    "code": "AF",
                    "currency_code": "AFN"
                },
                {
                    "id": 4,
                    "country": "Antigua and Barbuda",
                    "code": "AG",
                    "currency_code": "XCD"
                }
            ]

## Country [POST /general/addresses/countries/country]
Returns the country filtered by its ID.

+ Parameters
    + id: (integer, required) - Country ID
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": 129
            }

+ Response 200 (application/json)
    + Body

            {
                "id": 129,
                "country": "Sri Lanka",
                "code": "LK",
                "currency_code": "LKR"
            }