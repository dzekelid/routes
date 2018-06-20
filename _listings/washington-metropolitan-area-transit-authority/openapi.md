---
swagger: "2.0"
x-collection-name: Washington Metropolitan Area Transit Authority
x-complete: 1
info:
  title: Train Positions
  description: realtime-train-positions-and-support-methods-
  version: 1.0.0
host: api.wmata.com
basePath: /TrainPositions
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /StandardRoutes:
    get:
      summary: Standard Routes
      description: "Description\r\n\r\nReturns an ordered list of mostly revenue (and
        some lead) track circuits, arranged by line and track number.  This data does
        not change frequently and should be cached for a reasonable amount of time.\r\nPlease
        refer to this page for additional details.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStandardRoutes\r\n\r\n\r\nArray
        containing revenue line information (StandardRoute).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStandardRoute
        Elements\r\n\r\n\r\n\r\n\r\n\r\nLineCode\r\n\r\nAbbreviation for the revenue
        line.  Note that this also includes YLRP (Yellow Line Rush Plus).\r\n\r\n\r\n\r\nTrackCircuits\r\n\r\n\r\nArray
        containing ordered track circuit information (TrackCircuit).\r\n\r\n\r\n\r\n\r\nTrackNum\r\n\r\nTrack
        number (1 or 2).\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuit Elements\r\n\r\n\r\n
        \       \r\n\r\n\r\nCircuitId\r\n\r\nAn internal system-wide uniquely identifiable
        circuit number.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder in which the circuit appears
        for the given line and track.  Sequences go from West to East and South to
        North.\r\n        \r\n\r\n\r\nStationCode\r\n\r\nIf the circuit is at a station,
        this value will represent the station code.  Otherwise, it will be be NULL.
        Use this value in other rail-related APIs to retrieve data about a station."
      operationId: getStandardroutes
      x-api-path-slug: standardroutes-get
      parameters:
      - in: query
        name: contentType
        description: Returns response in the specified format
      responses:
        200:
          description: OK
      tags:
      - Transit
      - Subway
      - Routes
---