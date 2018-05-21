---
name: Washington Metropolitan Area Transit Authority
x-slug: washington-metropolitan-area-transit-authority
description: The collection of data offered here allows developers to create new and
  innovative applications for the web or mobile devices. We encourage you to integrate
  Metro data into your applications and mashups to help get people the information
  they want about getting around. Use of our APIs and other data is free of charge,
  you have two options, for new developers who want to try out the WMATA API but are
  not ready for production, and you can use our demonstration key, without having
  to register.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
x-kinRank: "8"
x-alexaRank: ""
tags: Routes
created: "2018-05-20"
modified: "2018-05-20"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/apis.md
specificationVersion: "0.14"
apis:
- name: WMATA Bus Route and Stop Methods JSON - Path Details
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nFor a given date, returns the set of ordered latitude/longitude
    points along\r\na route variant along with the list of stops served.\r\n\r\nResponse
    Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nStructures
    describing path/stop\r\ninformation.\r\n\r\nMost routes will return content in
    both Direction0 and\r\nDirection1 elements, though a few will return NULL for
    Direction0 or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no
    specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat
    the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive
    name for the route.\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route variant (e.g.: 10A,
    10Av1, etc.).\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated.
    Use the\r\nDirectionText element to denote the general direction of the route\r\nvariant.\r\n\r\n\r\n\r\nDirectionText\r\n\r\nGeneral
    direction of the route variant (NORTH, SOUTH, EAST,\r\nWEST, LOOP, etc.).\r\n\r\n\r\n\r\nShape\r\n\r\n\r\nArray
    containing shape point information (ShapePoint).\r\n\r\n\r\n\r\n\r\nStops\r\n\r\n\r\nArray
    containing stop information (Stop).\r\n\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive
    text of where the bus is headed. This is similar,\r\nbut not necessarily identical,
    to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\n\r\n\r\nShapePoint\r\nElements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder
    of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n\r\n\r\nStop Elements\r\n\r\n\r\n\r\n\r\n\r\nLat\r\n\r\nLatitude.\r\n\r\n\r\n\r\nLon\r\n\r\nLongitude.\r\n\r\n\r\n\r\nName\r\n\r\nStop
    name. May be slightly different from what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nRoutes\r\n\r\nString
    array of route variants which provide service at this\r\nstop. Note that these
    are not date-specific; any route variant\r\nwhich stops at this stop on any day
    will be listed.\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jRouteDetails
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutedetails-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutedetails-get-openapi.md
- name: WMATA Bus Route and Stop Methods JSON - Routes
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a list of all bus route variants (patterns).
    For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly
    different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray
    containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute
    Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique
    identifier for a given route variant. Can be used in\r\nvarious other bus-related
    methods.\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant\u2019s
    grouping \u2013 lines are a combination of routes which lie in the same corridor
    and which have significant portions of their paths along the same roadways."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jRoutes
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/jsonjroutes-get-openapi.md
- name: WMATA Bus Route and Stop Methods JSON - Schedule
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns schedules for a given route variant for
    a given date.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\n\r\nArrays
    containing trip information (Trip).\r\n\r\nMost routes will return content in
    both Direction0 and\r\nDirection1 elements, though a few (especially ones which
    run in\r\na loop, such as the U8) will return content only for Direction0\r\nand
    NULL content for Direction1.\r\n\r\n0 or 1 are binary properties. There is no
    specific mapping to\r\ndirection, but a different value for the same route signifies\r\nthat
    the route is in an opposite direction.\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive
    name for the route.\r\n\r\n\r\n\r\n\r\n\r\nTrip Elements\r\n\r\n\r\n\r\n\r\n\r\nDirectionNum\r\n\r\nDeprecated.
    Use the\r\nTripDirectionText element to denote the general direction of the\r\ntrip.\r\n\r\n\r\n\r\nEndTime\r\n\r\nScheduled
    end date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nRouteID\r\n\r\nBus route
    variant. This can be used in several other bus\r\nmethods which accept variants.\r\n\r\n\r\n\r\nStartTime\r\n\r\nScheduled
    start date and time (Eastern Standard Time) for this\r\ntrip. Will be in YYYY-MM-DDTHH:mm:ss
    format (e.g.:\r\n2014-10-27T13:17:00).\r\n\r\n\r\n\r\nStopTimes\r\n\r\n\r\nArray
    containing location and time information (StopTime).\r\n\r\n\r\n\r\n\r\nTripDirectionText\r\n\r\nGeneral
    direction of the trip (NORTH, SOUTH, EAST, WEST, LOOP,\r\netc.).\r\n\r\n\r\n\r\nTripHeadsign\r\n\r\nDescriptive
    text of where the bus is headed. This is similar,\r\nbut not necessarily identical,
    to what is displayed on the\r\nbus.\r\n\r\n\r\n\r\nTripID\r\n\r\nUnique trip ID.
    This can be correlated with the data returned\r\nfrom the schedule-related methods.\r\n\r\n\r\n\r\n\r\n\r\nStopTime
    Elements\r\n\r\n\r\n\r\n\r\n\r\nStopID\r\n\r\n7-digit regional ID which can be
    used in various bus-related\r\nmethods. If unavailable, the StopID will be 0 or
    NULL.\r\n\r\n\r\n\r\nStopName\r\n\r\nStop name. May be slightly different from
    what is spoken or\r\ndisplayed in the bus.\r\n\r\n\r\n\r\nStopSeq\r\n\r\nOrder
    of the stop in the sequence of StopTimes.\r\n\r\n\r\n\r\nTime\r\n\r\nScheduled
    departure date and time (Eastern Standard Time) from\r\nthis stop. Will be in
    YYYY-MM-DDTHH:mm:ss format (e.g.:\r\n2014-10-27T13:17:00)."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//json/jRouteSchedule
  tags: Buses,Routes,Schedules
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/jsonjrouteschedule-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/jsonjrouteschedule-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Path Details
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\nFor a given date, returns the set of ordered latitude/longitude
    points along route variant along with the list of stops served.\r\nResponse Elements\r\n\r\n\r\n\r\nElement\r\nDescription\r\n\r\n\r\n\r\n\r\nDirection0/Direction1\r\n\r\nStructures
    describing path/stopinformation.\r\n\r\nMost routes will return content in both
    Direction0 and Direction1 elements, though a few will return NULL for Direction0
    or for Direction1.\r\n\r\n0 or 1 are binary properties. There is no specific mapping
    to direction, but a different value for the same route signifies that the route
    is in an opposite direction.\r\n\r\n\r\n\r\nName\r\nDescriptive name for the route.\r\n\r\n\r\nRouteID\r\nBus
    route variant (e.g.: 10A, 10Av1, etc.).\r\n\r\n\r\n\r\n\r\nDirection0/Direction1
    Elements\r\n\r\n\r\n\r\n\r\nDirectionNum\r\nDeprecated. Use the DirectionText
    element to denote the general direction of the route variant.\r\n\r\n\r\nDirectionText\r\nGeneral
    direction of the route variant (NORTH, SOUTH, EAST, WEST, LOOP, etc.).\r\n\r\n\r\nShape\r\n\r\nArray
    containing shape point information (ShapePoint).\r\n\r\n\r\n\r\nStops\r\n\r\nArray
    containing stop information (Stop).\r\n\r\n\r\n\r\nTripHeadsign\r\nDescriptive
    text of where the bus is headed. This is similar, but not necessarily identical,
    to what is displayed on the bus.\r\n\r\n\r\n\r\n\r\nShapePoint Elements\r\n\r\n\r\n\r\n\r\nLat\r\nLatitude.\r\n\r\n\r\nLon\r\nLongitude.\r\n\r\n\r\nSeqNum\r\nOrder
    of the point in the sequence of ShapePoints.\r\n\r\n\r\n\r\n \r\nStop Elements\r\n\r\n\r\n\r\n\r\nLat\r\nLatitude.\r\n\r\n\r\nLon\r\nLongitude.\r\n\r\n\r\nName\r\nStop
    name. May be slightly different from what is spoken or displayed in the bus.\r\n\r\n\r\nRoutes\r\nString
    array of route variants which provide service at this stop. Note that these are
    not date-specific; any route variant which stops at this stop on any day will
    be listed.\r\n\r\n\r\nStopID\r\n7-digit regional ID which can be used in various
    bus-related methods. If unavailable, the StopID will be 0 or NULL."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//RouteDetails
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/routedetails-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/routedetails-get-openapi.md
- name: WMATA Bus Route and Stop Methods XML - Routes
  x-api-slug: wmata-bus-route-and-stop-methods
  description: "Description\r\n\r\nReturns a list of all bus route variants (patterns).
    For example, the 10A\r\nand 10Av1 are the same route, but may stop at slightly
    different locations.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nRoutes\r\n\r\n\r\nArray
    containing route variant information (Route).\r\n\r\n\r\n\r\n\r\n\r\n\r\nRoute
    Elements\r\n\r\n\r\n\r\n\r\n\r\nName\r\n\r\nDescriptive name of the route variant.\r\n\r\n\r\n\r\nRouteID\r\n\r\nUnique
    identifier for a given route variant. Can be used in\r\nvarious other bus-related
    methods.\r\n\r\n\r\n\r\n\r\nLineDescription\r\n\r\nDenotes the route variant\u2019s
    grouping \u2013 lines are a combination of routes which lie in the same corridor
    and which have significant portions of their paths along the same roadways."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc//Routes
  tags: Buses,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/routes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/routes-get-openapi.md
- name: WMATA Bus Route and Stop Methods
  x-api-slug: wmata-bus-route-and-stop-methods
  description: The collection of data offered here allows developers to create new
    and innovative applications for the web or mobile devices. We encourage you to
    integrate Metro data into your applications and mashups to help get people the
    information they want about getting around. Use of our APIs and other data is
    free of charge, you have two options, for new developers who want to try out the
    WMATA API but are not ready for production, and you can use our demonstration
    key, without having to register.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//Bus.svc
  tags: Routes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
- name: WMATA Train Positions Standard Routes
  x-api-slug: wmata-train-positions
  description: "Description\r\n\r\nReturns an ordered list of mostly revenue (and
    some lead) track circuits, arranged by line and track number.  This data does
    not change frequently and should be cached for a reasonable amount of time.\r\nPlease
    refer to this page for additional details.\r\n\r\nResponse Elements\r\n\r\n\r\n\r\n\r\nElement\r\n\r\nDescription\r\n\r\n\r\n\r\n\r\n\r\nStandardRoutes\r\n\r\n\r\nArray
    containing revenue line information (StandardRoute).\r\n\r\n\r\n\r\n\r\n\r\n\r\nStandardRoute
    Elements\r\n\r\n\r\n\r\n\r\n\r\nLineCode\r\n\r\nAbbreviation for the revenue line.
    \ Note that this also includes YLRP (Yellow Line Rush Plus).\r\n\r\n\r\n\r\nTrackCircuits\r\n\r\n\r\nArray
    containing ordered track circuit information (TrackCircuit).\r\n\r\n\r\n\r\n\r\nTrackNum\r\n\r\nTrack
    number (1 or 2).\r\n\r\n\r\n\r\n\r\n\r\nTrackCircuit Elements\r\n\r\n\r\n        \r\n\r\n\r\nCircuitId\r\n\r\nAn
    internal system-wide uniquely identifiable circuit number.\r\n\r\n\r\n\r\nSeqNum\r\n\r\nOrder
    in which the circuit appears for the given line and track.  Sequences go from
    West to East and South to North.\r\n        \r\n\r\n\r\nStationCode\r\n\r\nIf
    the circuit is at a station, this value will represent the station code.  Otherwise,
    it will be be NULL. Use this value in other rail-related APIs to retrieve data
    about a station."
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//TrainPositions//StandardRoutes
  tags: Transit,Subway,Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/standardroutes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/standardroutes-get-openapi.md
- name: WMATA Train Positions
  x-api-slug: wmata-train-positions
  description: The collection of data offered here allows developers to create new
    and innovative applications for the web or mobile devices. We encourage you to
    integrate Metro data into your applications and mashups to help get people the
    information they want about getting around. Use of our APIs and other data is
    free of charge, you have two options, for new developers who want to try out the
    WMATA API but are not ready for production, and you can use our demonstration
    key, without having to register.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/metro-developers.png
  humanURL: http://wmata.com/
  baseURL: https://api.wmata.com//TrainPositions
  tags: Routes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/washington-metropolitan-area-transit-authority/openapi.md
x-common:
- type: x-base
  url: http://api.wmata.com/
- type: x-developer
  url: http://developer.wmata.com/
- type: x-signup
  url: https://developer.wmata.com/signup/
- type: x-website
  url: http://wmata.com/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---