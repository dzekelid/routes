{
  "info": {
    "name": "PTV Timetable API - Version 3 Get V3 Routes",
    "_postman_id": "de66b8a1-a476-4374-b736-e3a0e3992bda",
    "description": "View route names and numbers for all routes.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Routes",
      "item": [
        {
          "id": "89247619-186a-458e-b3af-23f2e291c532",
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
              "id": "38c7e2b6-1d1a-4cff-9376-3d096ebff89a"
            }
          ]
        }
      ]
    }
  ]
}