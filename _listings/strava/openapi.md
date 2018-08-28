swagger: "2.0"
x-collection-name: Strava
x-complete: 1
info:
  title: Strava API v3
  description: strava-api
  version: 1.0.0
host: www.strava.com
basePath: /api/v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /athletes/{id}/routes:
    get:
      summary: List Athlete Routes
      description: Returns a list of the routes created by the authenticated athlete
        using their athlete ID.
      operationId: getRoutesByAthleteId
      x-api-path-slug: athletesidroutes-get
      parameters:
      - in: path
        name: id
        description: The identifier of the athlete
      - in: query
        name: No Name
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - List
      - Athlete
      - Routes
  /routes/{id}:
    get:
      summary: Get Route
      description: Returns a route using its identifier.
      operationId: getRouteById
      x-api-path-slug: routesid-get
      parameters:
      - in: path
        name: id
        description: The identifier of the route
      responses:
        200:
          description: Successful response
      tags:
      - Sports
      - Route