---
swagger: "2.0"
x-collection-name: Public Transport Victoria Timetable
x-complete: 0
info:
  title: PTV Timetable API - Version 3 Get V3 Routes Route
  description: View route name and number for specific route id.
  termsOfService: http://ptv.vic.gov.au/ptv-timetable-api/
  contact:
    name: Public Transport Victoria
    url: http://ptv.vic.gov.au/digital
  version: v3
host: timetableapi.ptv.vic.gov.au
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v3/routes:
    get:
      summary: Get V3 Routes
      description: View route names and numbers for all routes.
      operationId: Routes_OneOrMoreRoutes
      x-api-path-slug: v3routes-get
      parameters:
      - in: query
        name: devid
        description: Your developer id
      - in: query
        name: route_name
        description: Filter by name  of route (accepts partial route name matches)
      - in: query
        name: route_types
        description: Filter by route_type; values returned via RouteTypes API
      - in: query
        name: signature
        description: Authentication signature for request
      - in: query
        name: token
        description: Please ignore
      responses:
        200:
          description: OK
      tags:
      - Routes
  /v3/routes/{route_id}:
    get:
      summary: Get V3 Routes Route
      description: View route name and number for specific route id.
      operationId: Routes_RouteFromId
      x-api-path-slug: v3routesroute-id-get
      parameters:
      - in: query
        name: devid
        description: Your developer id
      - in: path
        name: route_id
        description: Identifier of route; values returned by Departures, Directions
          and Disruptions APIs
      - in: query
        name: signature
        description: Authentication signature for request
      - in: query
        name: token
        description: Please ignore
      responses:
        200:
          description: OK
      tags:
      - Routes
      - Route
      - Id
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---