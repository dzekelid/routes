---
name: Coord
x-slug: coord
description: Coord is a mobility company that creates seamless mobility and self-driving
  experiences today through deep integrations. The company offers bike-share API,
  Curbs API, Tolls API, Routing API and etc.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/coord-logo.png
x-kinRank: "7"
x-alexaRank: "1035226"
tags: Routes
created: "2018-08-28"
modified: "2018-08-28"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/coord/apis.md
specificationVersion: "0.14"
apis:
- name: Multimodal Routing API - Find a route.
  x-api-slug: route-get
  description: Find possible trips between two points using either or both of bike-share
    and transit.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/coord-logo.png
  humanURL: https://coord.co
  baseURL: https://api.coord.co//v1/routing
  tags: Parking, Tolls, Bikes, Routes, General Data, Relative Data, Service API
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/coord/route-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/coord/route-get-openapi.md
- name: Tolls API - Get all toll rates corresponding to a single route
  x-api-slug: route-post
  description: |-
    Returns information about the cost of a particular route due to tolls.

    Below is an example of a route:
    ```json
    {
      "departure_time": "2017-07-28T17:39:43.611Z",
      "steps": [
        {
          "polyline": [
            {"lat": 47.28348, "lng": -122.56066},
            {"lat": 47.28154, "lng": -122.56069},
            {"lat": 47.28000, "lng": -122.56075},
            {"lat": 47.27901, "lng": -122.56081},
            {"lat": 47.27900, "lng": -122.56081},
            {"lat": 47.27831, "lng": -122.56082},
            {"lat": 47.27823, "lng": -122.56082},
            {"lat": 47.27798, "lng": -122.56082}
          ]
        }
      ],
      "vehicle": {
        "axles": 2
      }
    }
    ```

    If you already have a list of waypoints along a route, you can use these directly, but if
    not, you can use a routing service like

    Google's Directions API
     to estimate the cost of travel between a given origin and destination.

    For example, imagine we are interested in the
    toll cost of a route between origin `47.287741,-122.561391` and
    destination `47.258214,-122.537900` (you may use street names instead of coordinates):

    * Make a request to Google's Directions API and get the route(s)
      between these two locations, e.g.:
      ```
      https://maps.googleapis.com/maps/api/directions/json?origin=47.287741,-122.561391&destination=47.258214,-122.537900
      ```
    * The result will be a JSON which includes one or more routes where each route has one or
      more legs and each leg has one or more steps:

      Therefore, if the result of above request is:
      ```json
      {...
        "routes": [
          {...
            "legs": [
              {...
                "steps": [
                  {
                    "duration": {
                      "text": "2 mins",
                      "value": 117
                    },
                    "html_instructions": "Head south on WA-16 EToll road",
                    "polyline": {
                      "points": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC"
                    },
                    "travel_mode": "DRIVING"
                  },
                  {
                    "duration": {
                      "text": "1 min",
                      "value": 38
                    },
                    "html_instructions": "Take exit 4 for Jackson Ave toward 6th AveToll road",
                    "polyline": {
                      "points": "o{m_Hhh}jVJCBA@AHIx@eA\\e@^g@lAiBp@iAf@{@|D{G\\o@`@q@n@gA`C{DNYHSDQFU"
                    },
                    "travel_mode": "DRIVING"
                  }
                ],
              }
            ], ...
          }
        ], ...
      }
      ```
    * For each route, iterate on all steps (of all legs) and create a `RouteStep`
      for each step, so that `encoded_polyline` is filled by `polyline.points`,
      `road_name` by `html_instructions`, and `duration` by `duration.value`. The result should look like:
      ```json
      {
        "steps": [
          {
            "encoded_polyline": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC",
            "road_name": "Head south on WA-16 E",
            "duration": "117s"
          },
          {
            "encoded_polyline": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC",
            "road_name": "Take exit 4 for Jackson Ave toward 6th Ave",
            "duration": "38s"
          }
        ],
        "departure_time": "2017-07-28T17:39:43.611Z",
        "vehicle": {
          "axles": 2
        }
      }
      ```

    Note: Google's `html_instructions` is not really equivalent to `road_name` but it usually
    contains road names. For simplicity, you can use `html_instructions` as road name. If
    your router provides road names then use that instead.

    Note: In case Google's Directions API returns `n` routes you will
    need to call the Tolls API `n` times, once per route.

    Note: The order of the steps should remain the same as the order returned
    by the router.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/coord-logo.png
  humanURL: https://coord.co
  baseURL: https://api.coord.co//v1/search/tolling
  tags: Parking, Tolls, Bikes, Routes, General Data, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/coord/route-post-openapi.md
- name: Tolls API - Get all toll rates corresponding to a single route
  x-api-slug: route-post
  description: |-
    Returns information about the cost of a particular route due to tolls.

    Below is an example of a route:
    ```json
    {
      "departure_time": "2017-07-28T17:39:43.611Z",
      "steps": [
        {
          "polyline": [
            {"lat": 47.28348, "lng": -122.56066},
            {"lat": 47.28154, "lng": -122.56069},
            {"lat": 47.28000, "lng": -122.56075},
            {"lat": 47.27901, "lng": -122.56081},
            {"lat": 47.27900, "lng": -122.56081},
            {"lat": 47.27831, "lng": -122.56082},
            {"lat": 47.27823, "lng": -122.56082},
            {"lat": 47.27798, "lng": -122.56082}
          ]
        }
      ],
      "vehicle": {
        "axles": 2
      }
    }
    ```

    If you already have a list of waypoints along a route, you can use these directly, but if
    not, you can use a routing service like

    Google's Directions API
     to estimate the cost of travel between a given origin and destination.

    For example, imagine we are interested in the
    toll cost of a route between origin `47.287741,-122.561391` and
    destination `47.258214,-122.537900` (you may use street names instead of coordinates):

    * Make a request to Google's Directions API and get the route(s)
      between these two locations, e.g.:
      ```
      https://maps.googleapis.com/maps/api/directions/json?origin=47.287741,-122.561391&destination=47.258214,-122.537900
      ```
    * The result will be a JSON which includes one or more routes where each route has one or
      more legs and each leg has one or more steps:

      Therefore, if the result of above request is:
      ```json
      {...
        "routes": [
          {...
            "legs": [
              {...
                "steps": [
                  {
                    "duration": {
                      "text": "2 mins",
                      "value": 117
                    },
                    "html_instructions": "Head south on WA-16 EToll road",
                    "polyline": {
                      "points": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC"
                    },
                    "travel_mode": "DRIVING"
                  },
                  {
                    "duration": {
                      "text": "1 min",
                      "value": 38
                    },
                    "html_instructions": "Take exit 4 for Jackson Ave toward 6th AveToll road",
                    "polyline": {
                      "points": "o{m_Hhh}jVJCBA@AHIx@eA\\e@^g@lAiBp@iAf@{@|D{G\\o@`@q@n@gA`C{DNYHSDQFU"
                    },
                    "travel_mode": "DRIVING"
                  }
                ],
              }
            ], ...
          }
        ], ...
      }
      ```
    * For each route, iterate on all steps (of all legs) and create a `RouteStep`
      for each step, so that `encoded_polyline` is filled by `polyline.points`,
      `road_name` by `html_instructions`, and `duration` by `duration.value`. The result should look like:
      ```json
      {
        "steps": [
          {
            "encoded_polyline": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC",
            "road_name": "Head south on WA-16 E",
            "duration": "117s"
          },
          {
            "encoded_polyline": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC",
            "road_name": "Take exit 4 for Jackson Ave toward 6th Ave",
            "duration": "38s"
          }
        ],
        "departure_time": "2017-07-28T17:39:43.611Z",
        "vehicle": {
          "axles": 2
        }
      }
      ```

    Note: Google's `html_instructions` is not really equivalent to `road_name` but it usually
    contains road names. For simplicity, you can use `html_instructions` as road name. If
    your router provides road names then use that instead.

    Note: In case Google's Directions API returns `n` routes you will
    need to call the Tolls API `n` times, once per route.

    Note: The order of the steps should remain the same as the order returned
    by the router.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/coord-logo.png
  humanURL: https://coord.co
  baseURL: https://api.coord.co//v1/search/tolling
  tags: Parking, Tolls, Bikes, Routes, General Data, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/coord/route-post-openapi.md
- name: Tolls API - Get all toll rates corresponding to a single route
  x-api-slug: route-post
  description: |-
    Returns information about the cost of a particular route due to tolls.

    Below is an example of a route:
    ```json
    {
      "departure_time": "2017-07-28T17:39:43.611Z",
      "steps": [
        {
          "polyline": [
            {"lat": 47.28348, "lng": -122.56066},
            {"lat": 47.28154, "lng": -122.56069},
            {"lat": 47.28000, "lng": -122.56075},
            {"lat": 47.27901, "lng": -122.56081},
            {"lat": 47.27900, "lng": -122.56081},
            {"lat": 47.27831, "lng": -122.56082},
            {"lat": 47.27823, "lng": -122.56082},
            {"lat": 47.27798, "lng": -122.56082}
          ]
        }
      ],
      "vehicle": {
        "axles": 2
      }
    }
    ```

    If you already have a list of waypoints along a route, you can use these directly, but if
    not, you can use a routing service like

    Google's Directions API
     to estimate the cost of travel between a given origin and destination.

    For example, imagine we are interested in the
    toll cost of a route between origin `47.287741,-122.561391` and
    destination `47.258214,-122.537900` (you may use street names instead of coordinates):

    * Make a request to Google's Directions API and get the route(s)
      between these two locations, e.g.:
      ```
      https://maps.googleapis.com/maps/api/directions/json?origin=47.287741,-122.561391&destination=47.258214,-122.537900
      ```
    * The result will be a JSON which includes one or more routes where each route has one or
      more legs and each leg has one or more steps:

      Therefore, if the result of above request is:
      ```json
      {...
        "routes": [
          {...
            "legs": [
              {...
                "steps": [
                  {
                    "duration": {
                      "text": "2 mins",
                      "value": 117
                    },
                    "html_instructions": "Head south on WA-16 EToll road",
                    "polyline": {
                      "points": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC"
                    },
                    "travel_mode": "DRIVING"
                  },
                  {
                    "duration": {
                      "text": "1 min",
                      "value": 38
                    },
                    "html_instructions": "Take exit 4 for Jackson Ave toward 6th AveToll road",
                    "polyline": {
                      "points": "o{m_Hhh}jVJCBA@AHIx@eA\\e@^g@lAiBp@iAf@{@|D{G\\o@`@q@n@gA`C{DNYHSDQFU"
                    },
                    "travel_mode": "DRIVING"
                  }
                ],
              }
            ], ...
          }
        ], ...
      }
      ```
    * For each route, iterate on all steps (of all legs) and create a `RouteStep`
      for each step, so that `encoded_polyline` is filled by `polyline.points`,
      `road_name` by `html_instructions`, and `duration` by `duration.value`. The result should look like:
      ```json
      {
        "steps": [
          {
            "encoded_polyline": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC",
            "road_name": "Head south on WA-16 E",
            "duration": "117s"
          },
          {
            "encoded_polyline": "m{r_Hnw`kVb@Qn@Up@Sr@QvAWjAO|@I^A^Mj@Ap@@v@?r@@hA@dB?bKDrHJdEJ@?hC@N?p@?`@?t@Cf@Gp@Kh@Kb@KXIVI`@O`@QXMd@WVOj@SZUf@_@b@c@l@s@vCwDfCiDjBkC~BcDlBiC|@mAZc@dPsTvCyDrEmGdEwFnDwErEiGdB}Bb@g@d@i@jBgC",
            "road_name": "Take exit 4 for Jackson Ave toward 6th Ave",
            "duration": "38s"
          }
        ],
        "departure_time": "2017-07-28T17:39:43.611Z",
        "vehicle": {
          "axles": 2
        }
      }
      ```

    Note: Google's `html_instructions` is not really equivalent to `road_name` but it usually
    contains road names. For simplicity, you can use `html_instructions` as road name. If
    your router provides road names then use that instead.

    Note: In case Google's Directions API returns `n` routes you will
    need to call the Tolls API `n` times, once per route.

    Note: The order of the steps should remain the same as the order returned
    by the router.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/coord-logo.png
  humanURL: https://coord.co
  baseURL: https://api.coord.co//v1/search/tolling
  tags: Parking, Tolls, Bikes, Routes, General Data, Relative Data, Service API
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/coord/route-post-openapi.md
x-common:
- type: x-blog
  url: https://medium.com/coord
- type: x-blog-rss
  url: https://medium.com/feed/coord
- type: x-openapi
  url: https://jsapi.apiary.io/apis/coordprodsearchtolls.source
- type: x-api-gallery
  url: http://convertapi.api.gallery.streamdata.io
- type: x-api-stack
  url: http://coord.stack.network
- type: x-developer
  url: https://coord.co/docs/
- type: x-pricing
  url: https://coord.co/#pricing
- type: x-twitter
  url: https://twitter.com/coordcity
- type: x-website
  url: https://coord.co
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---