{
  "info": {
    "name": "Transavia Routes API Get all routes by origin and/or destination",
    "_postman_id": "e128733e-c642-4dd6-8b34-99873369aaad",
    "description": "Retrieves all routes.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Airplanes",
      "item": [
        {
          "id": "86c0c903-cb1d-45d0-99cc-e0179b2e25f0",
          "name": "58d3ca3eab95b50fe4da10fd",
          "request": {
            "url": "http://tst.api.transavia.com/v3/routes/?Destination=%7B%7D&Origin=%7B%7D",
            "method": "GET",
            "header": [
              {
                "key": "Accept",
                "value": "*/*",
                "disabled": false
              }
            ],
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves all routes."
          },
          "response": [
            {
              "status": "Successful response",
              "code": 200,
              "name": "Response_200",
              "id": "f3ad8e7d-124c-4f8e-b396-4b7bcb12c29c"
            }
          ]
        }
      ]
    }
  ]
}