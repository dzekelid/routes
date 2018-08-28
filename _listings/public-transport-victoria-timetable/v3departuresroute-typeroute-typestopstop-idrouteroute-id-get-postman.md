{
  "info": {
    "name": "PTV Timetable API - Version 3 Get V3 Departures Route Type Route Type Stop Stop Route Route",
    "_postman_id": "410aba9f-d60a-4254-bbc6-a4b408c699db",
    "description": "View departures for a specific route from a stop.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Departures",
      "item": [
        {
          "id": "b7c6fcfc-2d4d-4d56-b256-f0100c59f1df",
          "name": "Departures_GetForStop",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/departures/route_type/:route_type/stop/:stop_id"
              ],
              "query": [
                {
                  "key": "date_utc",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "devid",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "direction_id",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "expand",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "gtfs",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "include_cancelled",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "max_results",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "platform_numbers",
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
                  "id": "route_type",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "stop_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View departures for all routes from a stop."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "2aaf60a6-7fed-4d58-8cd7-21dc8278f8a0"
            }
          ]
        },
        {
          "id": "6c1729b0-eb0c-4ade-b52b-3005986c6a17",
          "name": "Departures_GetForStopAndRoute",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/departures/route_type/:route_type/stop/:stop_id/route/:route_id"
              ],
              "query": [
                {
                  "key": "date_utc",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "devid",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "direction_id",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "expand",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "gtfs",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "include_cancelled",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "max_results",
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
                },
                {
                  "id": "route_type",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "stop_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View departures for a specific route from a stop."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6868a759-b24c-43d5-8603-1c2a48d68e04"
            }
          ]
        }
      ]
    }
  ]
}