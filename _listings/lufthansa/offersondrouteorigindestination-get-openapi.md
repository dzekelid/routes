---
swagger: "2.0"
x-collection-name: Lufthansa
x-complete: 0
info:
  title: LH Partner OND Route
  version: "1.0"
  description: Returns LH route origin & destination information
host: api.lufthansa.com
basePath: /v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /offers/ond/route/{origin}/{destination}:
    get:
      summary: OND Route
      description: Returns LH route origin & destination information
      operationId: offers.ond.route.origin.destination.get
      x-api-path-slug: offersondrouteorigindestination-get
      parameters:
      - in: header
        name: Accept
        description: 'Mandatory http header:  application/xml or application/json'
      - in: query
        name: catalogues
        description: Carrier for which the OND will be retrieved (e
      - in: path
        name: destination
        description: Enter either the destination city or country code (e
      - in: query
        name: limit
        description: Number of records returned per request
      - in: query
        name: offset
        description: Number of records skipped
      - in: path
        name: origin
        description: Enter either the orgin city or orgin country code (e
      responses:
        200:
          description: OK
      tags:
      - OND
      - Route
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