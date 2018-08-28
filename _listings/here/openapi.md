swagger: "2.0"
x-collection-name: HERE
x-complete: 1
info:
  title: Weather API
  description: the-here-weather-api-provides-weather-forecasts-and-reports-on-current-weather-conditions-provides-information-on-severe-weather-alerts-provides-information-about-when-the-sun-and-moon-rise-and-set-and-the-phase-of-the-moonthis-example-set-works-with-version-1-2-4-or-higheradditional-information-can-be-found-on-developer-here-comhttpsdeveloper-here-comrestapisdocumentationweather
  version: 1.0.0
host: weather.cit.api.here.com
basePath: /weather/1.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /route/corridor:
    get:
      summary: Find Locations along a pre-defined Route
      description: |-
        *Request a list of user-defined locations along a pre-defined route*

        The route has been pre-calculated and the `routeid` has already been acquired from a previous routing request. A route-based corridor search is requested using the `corridor` endpoint and by adding the `routeid` parameter to the request URL, along with a corridor `width`.



        * **layerId**  `text`
         \- Unique indicator used to retrieve a dataset

        * **routeId**  `text`
         \- A <b>previously</b> calculated routeId

        * **radius**  `number`
         \- Width of the search corridor

        * **limit**  `number`
         \- The limit of the number of items contained in the response.

        * **app_id**  `text`
         \- A 20 byte Base64 URL-safe encoded string used for the authentication of the client application.    You must include an `app_id` with every request.

        * **app_code**  `text`
         \- A 20 byte Base64 URL-safe encoded string used for the authentication of the client application.    You must include an `app_code` with every request.
      operationId: RouteCorridorGet
      x-api-path-slug: routecorridor-get
      parameters:
      - in: query
        name: app_code
      - in: query
        name: app_id
      - in: query
        name: layerId
      - in: query
        name: limit
      - in: query
        name: radius
      - in: query
        name: routeId
      responses:
        200:
          description: OK
      tags:
      - Find
      - Locations
      - Along
      - Pre-defined
      - Route
  /metarouter/rest/routeservice/v2/route.json:
    get:
      summary: Avoid Transit Routes Involving Transfers
      description: "*Request a direct public transit route excluding changes and transfers*\n\nPublic
        transit routes can be requested using the `metarouter/rest/routeservice/v2/route.json`
        endpoint. The `changes `parameter is used to indicate the number of changes
        or transfers desired. \n\n\n\n* **startX**  `number`\n \\- The longitude of
        the start point of your journey.    e.g. `13.377`\n\n* **startY**  `number`\n
        \\- The latitude of the start point of your journey.    e.g. `52.515`\n\n*
        **destX**  `number`\n \\- The longitude of the destination point of your journey.
        \   e.g. `13.377`\n\n* **destY**  `number`\n \\- The latitude of the destination
        point of your journey.    e.g. `52.515`\n\n* **time**  `text`\n \\- Time in
        format `yyyy-mm-ddThh:mm:ss`.\n\n* **app_id**  `text`\n \\- A 20 bytes Base64
        URL-safe encoded string used for the authentication of the client application.
        \   You must include an app_code and app_code with every request.\n\n* **app_code**
        \ `text`\n \\- A 20 bytes Base64 URL-safe encoded string used for the authentication
        of the client application.    You must include an app_code and app_code with
        every request.\n\n* **routing**  `enum`\n \\- Type of routing response required.
        \ tt: time-table routing, i.e. route response will show scheduled arrival/departure
        times of the transit at the stations.  sr: simple (or estimated) routing,
        i.e. route response will only show \nthe transit journey but without scheduled
        arrival/departure times.  all: for both estimated and time-table routing.
        \ Default: tt  \n\n    Valid values are : `tt`, `sr`, `all`\n\n* **changes**
        \ `enum`\n \\- Maximum number of changes or transfers. \n                Valid
        values: 0-6 or -1. Default: -1 (any number of transfers permitted).\n\n    >**NOTE:**
        In areas where this parameter is not supported the route response will show
        an attribute `sup_changes=0` in the `Connections` node.\n\n    Valid values
        are : `-1`, `0`, `1`, `2`, `3`, `4`, `5`, `6`"
      operationId: MetarouterRestRouteserviceV2RouteJsonGet8
      x-api-path-slug: metarouterrestrouteservicev2route-json-get
      parameters:
      - in: query
        name: app_code
      - in: query
        name: app_id
      - in: query
        name: changes
      - in: query
        name: destX
      - in: query
        name: destY
      - in: query
        name: routing
      - in: query
        name: startX
      - in: query
        name: startY
      - in: query
        name: time
      responses:
        200:
          description: OK
      tags:
      - Avoid
      - Transit
      - Routes
      - Involving
      - Transfers
  /getroute.json:
    get:
      summary: Previously calculated route information
      description: "*Request information about a previously calculated route*\n\nPrevious
        routes can be retrieved using the `getroute` endpoint and appending a `routeid`
        to the request. The `routeid` in question has been generated from a previous
        request. Note that server map updates usually invalidates `routeid` value
        computed on previous map versions. If it is the case, the `routeid` computation
        should be requested again on the map in current  use.\n  \n\n\n\n* **mode**
        \ `text`\n \\- Routing mode determines how the route is calculated.    e.g.
        `fastest;car;traffic:disabled.`  \n\n* **routeid**  `text`\n \\- Route identifier
        for which the detailed route information is being requested.  \n\n* **app_id**
        \ `text`\n \\- A 20 byte Base64 URL-safe encoded string used for the authentication
        of the client application.    You must include an `app_id` with every request.
        \ \n\n* **app_code**  `text`\n \\- A 20 byte Base64 URL-safe encoded string
        used for the authentication of the client application.    You must include
        an `app_code` with every request."
      operationId: GetrouteJsonGet
      x-api-path-slug: getroute-json-get
      parameters:
      - in: query
        name: app_code
      - in: query
        name: app_id
      - in: query
        name: mode
      - in: query
        name: routeid
      responses:
        200:
          description: OK
      tags:
      - Previously
      - Calculated
      - Route
      - Information
  /calculatematrix.json:
    get:
      summary: Many to many matrix routing
      description: "*Matrix routing request with three start points and five destinations*\n\nMatrix
        calculations are made using the `calculatematrix` endpoint and appending a
        three start parameters (`start0, ``start1, ``start2)` and multiple consecutively
        numbered `destination` parameters to the request.\n  \n\n\n\n* **start0**
        \ `latlng`\n \\- First start point for the route calculations.    e.g. `52.515,13.377`
        \ \n\n* **start1**  `latlng`\n \\- Second start point for the route calculations.
        \   e.g. `52.515,13.377`  \n\n* **start2**  `latlng`\n \\- Third start point
        for the route calculations.    e.g. `52.515,13.377`  \n\n* **destination0**
        \ `latlng`\n \\- First destination point for the route calculations.    e.g.
        `52.4,13.5`  \n\n* **destination1**  `latlng`\n \\- Second destination point
        for the route calculations.    e.g. `52.4,13.5`  \n\n* **destination2**  `latlng`\n
        \\- Third destination point for the route calculations.    e.g. `52.4,13.5`
        \ \n\n* **destination3**  `latlng`\n \\- Fourth destination point for the
        route calculations.    e.g. `52.4,13.5`    \n\n* **destination4**  `latlng`\n
        \\- Fifth destination point for the route calculations.    e.g. `52.4,13.5`
        \ \n\n* **mode**  `text`\n \\- Routing mode determines how the route is calculated.
        \   e.g. `fastest;car;traffic:disabled.`  \n\n* **app_id**  `text`\n \\- A
        20 byte Base64 URL-safe encoded string used for the authentication of the
        client application.    You must include an app_id with every request.    \n\n*
        **app_code**  `text`\n \\- A 20 byte Base64 URL-safe encoded string used for
        the authentication of the client application.    You must include an app_code
        with every request."
      operationId: CalculatematrixJsonGet2
      x-api-path-slug: calculatematrix-json-get
      parameters:
      - in: query
        name: app_code
      - in: query
        name: app_id
      - in: query
        name: destination0
      - in: query
        name: destination1
      - in: query
        name: destination2
      - in: query
        name: destination3
      - in: query
        name: destination4
      - in: query
        name: mode
      - in: query
        name: start0
      - in: query
        name: start1
      - in: query
        name: start2
      responses:
        200:
          description: OK
      tags:
      - Many
      - To
      - Many
      - Matrix
      - Routing