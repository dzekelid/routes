---
swagger: "2.0"
x-collection-name: Transavia
x-complete: 0
info:
  title: Transavia Routes API Get all routes by origin and/or destination
  description: Retrieves all routes.
  version: 1.0.0
host: tst.api.transavia.com
basePath: /v3/routes
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /:
    get:
      summary: Get all routes by origin and/or destination
      description: Retrieves all routes.
      operationId: 58d3ca3eab95b50fe4da10fd
      x-api-path-slug: get
      parameters:
      - in: query
        name: Destination
        description: IATA-code (3 characters) of the destination airport
      - in: query
        name: Origin
        description: IATA-code (3 characters) of the origin airport
      responses:
        200:
          description: Successful response
      tags:
      - Airplanes
      - Routes
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