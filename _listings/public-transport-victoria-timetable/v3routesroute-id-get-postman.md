{
  "info": {
    "name": "PTV Timetable API - Version 3 Get V3 Routes Route",
    "_postman_id": "ebd3103a-7140-4e0f-a812-a079ab4ef0c9",
    "description": "View route name and number for specific route id.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Routes",
      "item": [
        {
          "id": "582b76cc-49f2-4f2e-b4f9-a498b882e63d",
          "name": "Routes_OneOrMoreRoutes",
          "request": {
            "url": "http://timetableapi.ptv.vic.gov.au/v3/routes?devid=%7B%7D&route_name=%7B%7D&route_types=%7B%7D&signature=%7B%7D&token=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View route names and numbers for all routes."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "d1a9169c-bb2b-41ce-9ecc-3177e6f13226"
            }
          ]
        },
        {
          "id": "9297c51a-b81d-4aaf-be1e-e6d0bc723e1b",
          "name": "Routes_RouteFromId",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/routes/:route_id"
              ],
              "query": [
                {
                  "key": "devid",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "signature",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "token",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "route_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View route name and number for specific route id."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "27c2d414-9b35-4f68-9c46-02b8ed22212e"
            }
          ]
        }
      ]
    }
  ]
}