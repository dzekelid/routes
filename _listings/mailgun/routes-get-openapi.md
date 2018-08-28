---
swagger: "2.0"
x-collection-name: Mailgun
x-complete: 0
info:
  title: Mailgun API Routes
  description: Fetches the list of routes. Note that routes are defined globally,
    per account, not per domain as most of other API calls.
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