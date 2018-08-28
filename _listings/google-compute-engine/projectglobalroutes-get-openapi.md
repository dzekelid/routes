---
swagger: "2.0"
x-collection-name: Google Compute Engine
x-complete: 0
info:
  title: Google Compute Engine API Get Routes
  description: Retrieves the list of Route resources available to the specified project.
  contact:
    name: Google
    url: https://google.com
  version: v1
host: www.googleapis.com
basePath: /compute/v1/projects
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /{project}/global/routes:
    get:
      summary: Get Routes
      description: Retrieves the list of Route resources available to the specified
        project.
      operationId: compute.routes.list
      x-api-path-slug: projectglobalroutes-get
      parameters:
      - in: query
        name: filter
        description: Sets a filter expression for filtering listed resources, in the
          form filter={expression}
      - in: query
        name: maxResults
        description: The maximum number of results per page that should be returned
      - in: query
        name: orderBy
        description: Sorts list results by a certain order
      - in: query
        name: pageToken
        description: Specifies a page token to use
      - in: path
        name: project
        description: Project ID for this request
      responses:
        200:
          description: OK
      tags:
      - Route
    post:
      summary: Create Route
      description: Creates a Route resource in the specified project using the data
        included in the request.
      operationId: compute.routes.insert
      x-api-path-slug: projectglobalroutes-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: project
        description: Project ID for this request
      responses:
        200:
          description: OK
      tags:
      - Route
  /{project}/global/routes/{route}:
    delete:
      summary: Delete Route
      description: Deletes the specified Route resource.
      operationId: compute.routes.delete
      x-api-path-slug: projectglobalroutesroute-delete
      parameters:
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: route
        description: Name of the Route resource to delete
      responses:
        200:
          description: OK
      tags:
      - Route
    get:
      summary: Get Route
      description: Returns the specified Route resource. Get a list of available routes
        by making a list() request.
      operationId: compute.routes.get
      x-api-path-slug: projectglobalroutesroute-get
      parameters:
      - in: path
        name: project
        description: Project ID for this request
      - in: path
        name: route
        description: Name of the Route resource to return
      responses:
        200:
          description: OK
      tags:
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