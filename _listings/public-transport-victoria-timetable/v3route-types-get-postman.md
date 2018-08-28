{
  "info": {
    "name": "PTV Timetable API - Version 3 Get V3 Route Types",
    "_postman_id": "8ec8a0dd-d458-4c23-9fa8-da2cce3ac327",
    "description": "View all route types and their names.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Route",
      "item": [
        {
          "id": "c9454752-3437-43b2-b64a-7195de4307dc",
          "name": "RouteTypes_GetRouteTypes",
          "request": {
            "url": "http://timetableapi.ptv.vic.gov.au/v3/route_types?devid=%7B%7D&signature=%7B%7D&token=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View all route types and their names."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "e743a78f-e3b2-4f2b-8e88-8e4d5a1af82a"
            }
          ]
        }
      ]
    }
  ]
}