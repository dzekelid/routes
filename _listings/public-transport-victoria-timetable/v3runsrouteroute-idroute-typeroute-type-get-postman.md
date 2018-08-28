{
  "info": {
    "name": "PTV Timetable API - Version 3 Get V3 Runs Route Route Route Type Route Type",
    "_postman_id": "f9748571-b8e8-4578-b8cb-b739c2a4c729",
    "description": "View all trip/service runs for a specific route id and route type.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Departures",
      "item": [
        {
          "id": "c0e421e5-25f9-417d-b1f3-7fe0edead4ad",
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
              "id": "1621343a-0e82-4242-839b-e33c6f742877"
            }
          ]
        },
        {
          "id": "901d7049-0667-4254-9803-9f3dc27607f3",
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
              "id": "95010fba-27fe-431b-9e12-1e2abcc2e276"
            }
          ]
        }
      ]
    },
    {
      "name": "Directions",
      "item": [
        {
          "id": "4e5f837c-e216-4b25-887b-20a723f3809f",
          "name": "Directions_ForRoute",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/directions/route/:route_id"
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
            "description": "View directions that a route travels in."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "8a2d5b32-965e-49f1-a569-2e5fbc84de26"
            }
          ]
        },
        {
          "id": "d878d6ae-c6c8-4e21-b17f-ddee341deaad",
          "name": "Directions_ForDirection",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/directions/:direction_id"
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
                  "id": "direction_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View all routes for a direction of travel."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "36c3b4d7-bfd7-4811-a3eb-d52ac3603c7e"
            }
          ]
        },
        {
          "id": "36b7ab86-ecda-49a5-a1ad-b82df024c3b1",
          "name": "Directions_ForDirectionAndType",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/directions/:direction_id/route_type/:route_type"
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
                  "id": "direction_id",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "route_type",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View all routes of a particular type for a direction of travel."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a06d61c6-9ea2-45da-8a7d-9111bdcf172b"
            }
          ]
        }
      ]
    },
    {
      "name": "Disruptions",
      "item": [
        {
          "id": "2d406ac9-344d-46be-967b-bec18f02b690",
          "name": "Disruptions_GetAllDisruptions",
          "request": {
            "url": "http://timetableapi.ptv.vic.gov.au/v3/disruptions?devid=%7B%7D&disruption_status=%7B%7D&route_types=%7B%7D&signature=%7B%7D&token=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View all disruptions for all route types."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "726b6842-f350-45d4-b0c7-ca7596eb16ec"
            }
          ]
        },
        {
          "id": "ce3ccb8f-d6de-4250-93e1-f2f8f1e8a10a",
          "name": "Disruptions_GetDisruptionsByRoute",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/disruptions/route/:route_id"
              ],
              "query": [
                {
                  "key": "devid",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "disruption_status",
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
            "description": "View all disruptions for a particular route."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "05239d40-1713-4876-9785-84b9c1240f65"
            }
          ]
        },
        {
          "id": "65820f2d-7b6d-449c-ac72-acf5f244bc60",
          "name": "Disruptions_GetDisruptionById",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/disruptions/:disruption_id"
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
                  "id": "disruption_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View a specific disruption."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "fed8f64c-7b44-4e43-8cf5-4821e3adb32f"
            }
          ]
        }
      ]
    },
    {
      "name": "Pattern",
      "item": [
        {
          "id": "391d85a4-36c3-4689-9282-8c0e3a14e946",
          "name": "Patterns_GetPatternByRun",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/pattern/run/:run_id/route_type/:route_type"
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
                  "key": "signature",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "stop_id",
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
                  "id": "run_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View the stopping pattern for a specific trip/service run."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "e96b1d81-a916-4896-b7de-6144276ae8c8"
            }
          ]
        }
      ]
    },
    {
      "name": "Route",
      "item": [
        {
          "id": "ab3f367e-c4f6-4058-aa1e-4def67e3062b",
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
              "id": "d4f3461c-c767-494e-8cf1-9558402f4acd"
            }
          ]
        }
      ]
    },
    {
      "name": "Routes",
      "item": [
        {
          "id": "f7288aa7-4952-423b-84f8-00f808813105",
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
              "id": "853c30f0-1688-4ca1-a11a-22cf40bbb64f"
            }
          ]
        },
        {
          "id": "eb491dae-49b1-45d5-bbb2-aa2d7c9f5edf",
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
              "id": "09fe604f-ec01-4756-b9a0-fbb0fa0ba777"
            }
          ]
        }
      ]
    },
    {
      "name": "Runs",
      "item": [
        {
          "id": "02081f9a-c14c-49d8-827e-0a4bb0d53b25",
          "name": "Runs_ForRoute",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/runs/route/:route_id"
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
            "description": "View all trip/service runs for a specific route id."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "3b10f848-6a74-4601-a433-b13490c097ba"
            }
          ]
        },
        {
          "id": "e539d0ae-1af0-4bc1-948e-dd9da38ad86e",
          "name": "Runs_ForRouteAndRouteType",
          "request": {
            "url": {
              "protocol": "http",
              "host": "timetableapi.ptv.vic.gov.au",
              "path": [
                "v3/runs/route/:route_id/route_type/:route_type"
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
                },
                {
                  "id": "route_type",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "View all trip/service runs for a specific route id and route type."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "71d5b58f-320e-4f64-ac11-70fd2587ef84"
            }
          ]
        }
      ]
    }
  ]
}