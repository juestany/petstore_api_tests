# Petstore API Tests

This repository contains automated tests for the Swagger Petstore API https://petstore.swagger.io/v2 using Postman. 
The API's three domains are `pet`, `store` and `user`.

---

## Requirements
- Postman or Postman Web
- Newman CLI for running tests through the terminal
- Optional: newman-reporter-htmlextra for a clear HTML report

----

## Usage

1. Install Newman:
```bash
npm install -g newman
```

Optional: install newman-reporter-htmlextra
```bash
npm install -g newman-reporter-htmlextra
```

2. Run the collection:
```bash
newman run Petstore_API_Tests.postman_collection.json
```

----

## Test structure
The collection is organised into 3 folders, each representing an API module:

- `pet` - CRUD operations for pet objects, image uploads, status queries, etc.
- `store` - Operations related to orders, inventories, and order deletion.
- `user` - Covers registration, login/logout, updating and deleting users.

Also, each folder contains both **positive** and **negative** scenarios (to simulate bad inputs and error responses).

----

## Features
- Test for all documented enpoints in the Swagger Petstore API
- Validation of HTTP response codes (200, 400, 404, 405)
- Global variables set dynamically

----

## Notes 
Due to the API design and its server overload, some tests (either positive or negative) don't behave as excepted and without changing the input data, the tests sometimes pass, and sometimes fail.
