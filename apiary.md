FORMAT: 1A

# FX Hello

# Authentication [/auth]
Authentication related operations.

## Login [POST /auth/login]
Allows the user to login using their email address and the password. The API will return a JSON Web Token (JWT) upon successful login. This token needs to be sent in the header of each call of the API.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "email": "user@example.com",
                "password": "Abc@1234"
            }

+ Response 200 (application/json)
    + Body

            {
                "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1",
                "isError": false
            }

# Authentication [/auth]
Authentication related operations.

## Register [POST /auth/register]
Allows user to create an account

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "name": "John",
                "email": "john@example.com",
                "password": "Abc@1234",
                "password_confirmation": "Abc@1234"
            }

+ Response 200 (application/json)
    + Body

            {
                "user": {
                    "name": "John",
                    "email": "john@example.com",
                    "updated_at": "2016-11-21 05:56:03",
                    "created_at": "2016-11-21 05:56:03",
                    "id": 1640,
                    "tax_rate": "0.00"
                },
                "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1",
                "isError": false
            }

## Refresh token [GET /auth/refreshToken]
Refreshes the existing token with a new token with a new expiration. Token will be returned as the response.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

+ Response 200 (application/json)
    + Body

            {
                "token": "5805a3536b0bdc039843aff2"
            }

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

+ Parameters
    + sendImage: (boolean, optional) - Whether the server should return the serve-able image URL or not.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "customerId": "546813a68bc6"
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
                "cuName": "Anushan",
                "uuid": 1,
                "uuName": "Anushan",
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
                "cuName": "Anushan",
                "uuid": 1,
                "uuName": "Anushan",
                "updated_at": "2017-05-18 05:05:12",
                "created_at": "2017-05-18 05:05:12",
                "_id": "591d2b884189dc52725cc042"
            }

# Stores [/stores]
Stores related operations.

## Stores [POST /stores/stores]
Returns the full list of warehouses

+ Parameters
    + type: (string, optional) - The type of store that should be retrieved. If not defined, all stores will be returned.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
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
    + telephone1: (string, optional) - 
    + telephone2: (string, optional) - 
    + fax: (string, optional) - 
    + email: (string, optional) - 
    + description: (string, optional) - 
    + status: (integer, optional) - Status of the store
        + Default: 1

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
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

# Stock Transfers [/stock/transfers]
Stock transfers related operations.

## Transfer between stores [POST /stock/transfers/transfer]
User can transfer stock between stores.

+ Parameters
    + from: (string, required) - Store id of the store where the items are moving out of.
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

# Products [/products]
Products related operations.

## Products list [POST /products/products]
Returns a list of products of the organization.

+ Parameters
    + sendImage: (boolean, optional) - Whether a publicly accessible URL needed or not. Link is valid only for 1 Hour.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

## Product [POST /products/products/product]
Returns the data of a product by passing the product ID.

+ Parameters
    + id: (string, required) - Product ID
    + sendImage: (boolean, optional) - Whether a publicly accessible URL needed or not. Link is valid only for 1 Hour.
        + Default: 

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "id": "580083186b0bdc05ff588792",
                "sendImage": false
            }

## Create product [POST /products/products/product/create]
Create a new product by posting product information.

+ Parameters
    + sku: (string, optional) - Product SKU
    + barcode: (string, optional) - 
    + name: (string, optional) - Product name
    + category: (string, optional) - Category ID
    + weight: (float, optional) - 
    + weightUnit: (string, optional) - 
    + purchasePrice: (float, optional) - 
    + price: (float, optional) - 
    + thresholdPrice: (float, optional) - 
    + lowestPrice: (float, optional) - 
    + priceCode: (string, optional) - 
    + productInfo: (string, optional) - 
    + productUrl: (string, optional) - 
    + description: (string, optional) - 
    + brandName: (string, optional) - 
    + width: (float, optional) - 
    + depth: (float, optional) - 
    + height: (float, optional) - 
    + lengthUnit: (string, optional) - 
    + creditPeriod: (integer, optional) - 
    + status: (integer, optional) - 

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
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

## Remove RFID from product (by RFID) [POST /products/product/remove-rfid]
Remove the RFID of a product by passing the EPC and TID. If the confirm parameter is sent as true, the EPC and TID will be removed. If confirm parameter is sent as false, the product matching the TID and EPC will be returned and record shall not be affected.

+ Parameters
    + tid: (string, required) - RFID TID
    + epc: (string, required) - RFID EPC
    + confirm: (boolean, optional) - If true, the RFID will be removed from the product. If false the product will be returned.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
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
    + name: (string, optional) - 
    + category: (string, optional) - 
    + weight: (float, optional) - 
    + weightUnit: (string, optional) - 
    + price: (float, optional) - 
    + thresholdPrice: (float, optional) - 
    + lowestPrice: (float, optional) - 
    + purchasePrice: (float, optional) - 
    + priceCode: (string, optional) - 
    + productInfo: (string, optional) - 
    + productUrl: (string, optional) - 
    + description: (string, optional) - 
    + brandName: (string, optional) - 
    + width: (float, optional) - 
    + depth: (float, optional) - 
    + height: (float, optional) - 
    + lengthUnit: (string, optional) - 
    + lengthUnit: (integer, optional) - 
    + creditperiod: (integer, optional) - Credit period for the product in number of days

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "sendImage": false
            }

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

# Purchase Orders [/purchasing/orders]
Purchase order related operations.

## Purchase order list [POST /purchasing/orders]
Returns a list of purchase orders of the organization.

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

## Purchase order [POST /purchasing/orders/order]
Returns a purchase orders of the organization by it's ID.

+ Parameters
    + id: (string, required) - ID of the purchase order

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
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

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG

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