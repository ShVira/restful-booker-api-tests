# Restful-Booker API tests

API tests for Restful-Booker, a practice booking API made for testers. I wrote them in Postman.

- API: https://restful-booker.herokuapp.com
- API docs: https://restful-booker.herokuapp.com/apidoc/index.html

## Files

- `Restful-Booker.postman_collection.json`: 24 requests with tests
- `Restful-Booker.postman_environment.json`: base URL and the test login from the API docs
- `API_Test_Cases.xlsx`: the same checks as a test case list with request and expected result

## What is covered

- Auth: getting a token with valid credentials, wrong password and empty body
- Booking: list of bookings, booking by id, search by name, create, update (PUT), partial update (PATCH), delete
- Access: update and delete without a token and with an invalid token
- Validation: missing and empty firstname, negative price, price as text, checkout before checkin, invalid date
- Not found: get and update a booking that does not exist, get a deleted booking

Every request checks the status code. Where it makes sense, tests also check the response body, for example that the saved data is the same as in the request.

The token and the booking id are saved to environment variables and used in the next requests, so the collection has to run in order.

## How to run

In Postman:

1. Import both json files
2. Select the "Restful-Booker" environment
3. Open the collection and click Run

From the command line with Newman:

```
npm install -g newman
newman run Restful-Booker.postman_collection.json -e Restful-Booker.postman_environment.json
```

## Author

Vira Shkurenko, Junior QA Engineer. [LinkedIn](https://linkedin.com/in/vira-shkurenko)
