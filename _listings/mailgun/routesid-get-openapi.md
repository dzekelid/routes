---
swagger: "2.0"
x-collection-name: Mailgun
x-complete: 0
info:
  title: Mailgun API Route
  description: Returns a single route object based on its ID.
  version: v2
host: api.mailgun.net
basePath: v2/
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  routes/:
    get:
      summary: Routes
      description: Fetches the list of routes. Note that routes are defined globally,
        per account, not per domain as most of other API calls.
      operationId: getRoutes
      x-api-path-slug: routes-get
      responses:
        200:
          description: OK
      tags:
      - Routes
    post:
      summary: Add Route
      description: Creates a new route.
      operationId: postRoutes
      x-api-path-slug: routes-post
      parameters:
      - in: query
        name: action
        description: Route action
      - in: query
        name: description
        description: An arbitrary string
      - in: query
        name: expression
        description: A filter expression like match_recipient(
      - in: query
        name: priority
        description: 'Integer: smaller number indicates higher priority'
      responses:
        200:
          description: OK
      tags:
      - Route
  routes/{id}:
    delete:
      summary: Delete Route
      description: Deletes a route based on the id.
      operationId: deleteRoutes
      x-api-path-slug: routesid-delete
      parameters:
      - in: path
        name: id
        description: ID of the route
      responses:
        200:
          description: OK
      tags:
      - Route
    get:
      summary: Route
      description: Returns a single route object based on its ID.
      operationId: getRoutes
      x-api-path-slug: routesid-get
      responses:
        200:
          description: OK
      tags:
      - Route
    put:
      summary: Updates Route
      description: Updates a given route by ID.
      operationId: putRoutes
      x-api-path-slug: routesid-put
      parameters:
      - in: query
        name: action
        description: Route action
      - in: query
        name: description
        description: An arbitrary string
      - in: query
        name: expression
        description: A filter expression like match_recipient(
      - in: path
        name: id
        description: ID of the route
      - in: query
        name: priority
        description: 'Integer: smaller number indicates higher priority'
      responses:
        200:
          description: OK
      tags:
      - S
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