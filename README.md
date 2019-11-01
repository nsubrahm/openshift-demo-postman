# Introduction

This repository stores a Postman collection to test the APIs.

## Steps

1. Import the [Collection](collection/openshift-demo-postman.json) into Postman.
2. Ensure that the URL has the value as seen in the `Route` object.
3. Run the `POST` request to add a new customer to the databse.
   1. You may change values in the request body.
   2. Note the key value returned in `message` object of the response body.
4. Run the `GET` request with customer ID as received in `POST` request.
   1. The result should be same as the one used in `POST`.
5. Run the `PUT` request with customer ID as received in `POST` request.
   1. You may change values in the request body.
6. Run the `GET` request with customer ID as received in `POST` request.
   1. The result should be same as the one used in `PUT`.
7. Run the `DELETE` request with customer ID as received in `POST` request.
8. Run the `GET` request with customer ID as received in `POST` request.
   1. The result should be a response with HTTP status code `404`.

## Equivalent `curl` commands

1. Ensure that the URL has the value as seen in the `Route` object.
2. Add a customer

```bash
curl -X POST http://custdemo-apis-custdemo.192.168.99.100.nip.io/customers  -d '{"name":"OpenShiftDemo","address":"Hebbala, Bengaluru, INDIA"}'
```

3. Get a customer
   1. Replace `customerId` below with the ID returned in the `POST` request.

```bash
curl -X GET http://custdemo-apis-custdemo.192.168.99.100.nip.io/customer/customerId
```

4. Edit details of a customer
   1. Replace `customerId` below with the ID returned in the `POST` request.

```bash
curl -X PUT http://custdemo-apis-custdemo.192.168.99.100.nip.io/customer/customerId -d '{"name":"OpenShiftDemo","address":"Indiranagara, Bengaluru, INDIA"}'
```

5. Remove of a customer
   1. Replace `customerId` below with the ID returned in the `POST` request.

```bash
curl -X DELETE http://custdemo-apis-custdemo.192.168.99.100.nip.io/customer/customerId
```
