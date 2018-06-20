---
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
---