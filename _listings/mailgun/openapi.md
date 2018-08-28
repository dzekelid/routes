swagger: "2.0"
x-collection-name: Mailgun
x-complete: 1
info:
  title: Mailgun API
  description: powerful-apis-that-allow-you-to-send-receive-and-track-email-effortlessly-
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