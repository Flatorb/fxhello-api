FORMAT: 1A

# FXHello

# Tasks [/tasks]
Tasks related operations.

## Create a new task [POST /tasks/create]
Allows the user the create a new task

+ Request (application/json)
    + Headers

            Accept: application/vnd.fxhello.v1+json
            Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbG
    + Body

            {
                "name": "This is the task name",
                "description": "Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor.",
                "dueDate": "2017-10-23 14:23:00",
                "priority": 3,
                "type": 17,
                "typeId": "46ab4658f88e8d8"
            }

+ Response 200 (application/json)
    + Body

            {
                "id": "5805a3536b0bdc039843aff2"
            }

# Authentication
Authentication related operations.

## Login [POST /authenticate]
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

# Warehouse [/warehouses]
Warehouses related operations.

## Stores [POST /warehouses/stores]
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