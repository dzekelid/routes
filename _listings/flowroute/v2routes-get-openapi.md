---
swagger: "2.0"
x-collection-name: Flowroute
x-complete: 0
info:
  title: FlowRoute API List Inbound Routes
  description: Returns a list of your inbound routes. From the list, you can then
    select routes to use as the primary and failover routes for a phone number, which
    you can do via "Update Primary Voice Route for a Phone Number" and "Update Failover
    Voice Route for a Phone Number".
  version: 1.0.0
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /v2/routes:
    get:
      summary: List Inbound Routes
      description: Returns a list of your inbound routes. From the list, you can then
        select routes to use as the primary and failover routes for a phone number,
        which you can do via "Update Primary Voice Route for a Phone Number" and "Update
        Failover Voice Route for a Phone Number".
      operationId: returns-a-list-of-your-inbound-routes-from-the-list-you-can-then-select-routes-to-use-as-the-primary
      x-api-path-slug: v2routes-get
      parameters:
      - in: query
        name: limit
        description: Limits the number of routes to retrieve
      - in: query
        name: offset
        description: Offsets the list of routes by your specified value
      - in: query
        name: route_type
        description: Restricts the results to inbound routes with your specified route
          type
      responses:
        200:
          description: OK
      tags:
      - Messaging
      - List
      - Inbound
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