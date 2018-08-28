swagger: "2.0"
x-collection-name: Transport for London Unified
x-complete: 1
info:
  title: Transport for London Unified
  description: our-unified-api-brings-together-data-across-all-modes-of-transport-into-a-single-restful-api--this-api-provides-access-to-the-most-highly-requested-realtime-and-status-infomation-across-all-the-modes-of-transport-in-a-single-and-consistent-way--access-to-the-developer-documentation-is-available-at-httpsapi-tfl-gov-uk
  version: v1
host: api.tfl.gov.uk
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /Line/Mode/{modes}/Route:
    get:
      summary: Line  Mode modes  Route
      description: Gets all lines and their valid routes for given modes, including
        the name and id of the originating and terminating stops for each route.
      operationId: Line_RouteByMode
      x-api-path-slug: linemodemodesroute-get
      parameters:
      - in: path
        name: modes
        description: A comma-separated list of modes e
      - in: query
        name: serviceTypes
        description: A comma seperated list of service types to filter on
      responses:
        200:
          description: OK
      tags:
      - Line
      - ""
      - Mode
      - Modes
      - ""
      - Route
  /Line/Route:
    get:
      summary: Line  Route
      description: Get all valid routes for all lines, including the name and id of
        the originating and terminating stops for each route..
      operationId: Line_Route
      x-api-path-slug: lineroute-get
      parameters:
      - in: query
        name: serviceTypes
        description: A comma seperated list of service types to filter on
      responses:
        200:
          description: OK
      tags:
      - Line
      - ""
      - Route
  /Line/{ids}/Route:
    get:
      summary: Line s  Route
      description: Get all valid routes for given line ids, including the name and
        id of the originating and terminating stops for each route..
      operationId: Line_LineRoutesByIds
      x-api-path-slug: lineidsroute-get
      parameters:
      - in: path
        name: ids
        description: A comma-separated list of line ids e
      - in: query
        name: serviceTypes
        description: A comma seperated list of service types to filter on
      responses:
        200:
          description: OK
      tags:
      - Line
      - S
      - ""
      - Route
  /Line/{id}/Route/Sequence/{direction}:
    get:
      summary: Line  Route  Sequence direction
      description: Gets all valid routes for given line id, including the sequence
        of stops on each route..
      operationId: Line_RouteSequence
      x-api-path-slug: lineidroutesequencedirection-get
      parameters:
      - in: path
        name: direction
        description: The direction of travel
      - in: query
        name: excludeCrowding
        description: That excludes crowding from line disruptions
      - in: path
        name: id
        description: A single line id e
      - in: query
        name: serviceTypes
        description: A comma seperated list of service types to filter on
      responses:
        200:
          description: OK
      tags:
      - Line
      - ""
      - Route
      - ""
      - Sequence
      - Direction
  /StopPoint/{id}/Route:
    get:
      summary: Stop Point  Route
      description: Returns the route sections for all the lines that service the given
        stop point ids.
      operationId: StopPoint_Route
      x-api-path-slug: stoppointidroute-get
      parameters:
      - in: path
        name: id
        description: A stop point id (station naptan codes e
      - in: query
        name: serviceTypes
        description: A comma-separated list of service types to filter on
      responses:
        200:
          description: OK
      tags:
      - Stop
      - Point
      - ""
      - Route