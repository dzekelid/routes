swagger: "2.0"
x-collection-name: Coord
x-complete: 1
info:
  title: Users API
  description: the-users-api-allows-you-to-manage-user-data-on-the-coord-platform--sending-user-data-to-coordallows-you-to-perform-transactions-with-mobility-systems-like-renting-a-bike-parking-ina-parking-lot-or-booking-a-ridehail-trip-on-behalf-of-that-user-using-the-coord-platform-the-requirements-for-performing-a-transaction-for-a-given-user-vary-depending-on-the-systemyoure-connecting-with--some-systems-require-particular-data-about-a-user-in-order-for-thetransaction-to-take-place-and-some-systems-require-you-to-link-a-users-account--alltransactions-require-you-to-authenticate-the-user-using-a-jwt-every-coord-api-that-supports-transactions-has-an-endpoint-for-getting-information-aboutthat-apis-systems-along-with-what-you-need-to-provide-for-a-user-in-order-to-perform-atransaction-for-them--the-users-api-provides-tools-that-help-you-enable-users-to-performtransactions-as-well-as-tools-for-learning-about-the-transactions-that-a-user-can-alreadyperform-read-on-for-more-information-about-authenticating-users-linking-accounts-and-managing-userdata--authenticating-users-with-jwtsall-coord-api-endpoints-that-either-manipulate-data-or-perform-a-transaction-on-behalf-of-alogged-in-user-require-http-calls-to-include-an-authorization-bearer-jwt-token-so-thatthe-current-user-can-be-identified--all-endpoints-in-the-users-api-fall-into-this-categoryexcept-for-the-test-jwt-creation-endpoint-which-is-designed-to-allow-you-to-create-test-tokensfor-use-in-such-requests-for-information-on-how-to-create-nontest-user-authorization-tokensplease-contact-a-hrefmailtosalescoord-co-target-blanksalescoord-coaas-this-is-available-only-for-transaction-enabled-partners-see-post-v1userstestinguser-and-jwtreference0testjwtcreation-for-information-onhow-to-create-jwts-for-testing--linking-accountsmany-systems-require-you-to-link-a-user-in-order-to-perform-a-transaction--you-can-do-this-byredirecting-the-users-browser-or-webview-to-theget-v1userslink-accountreference0linkauseraccounttoenabletransactions-endpoint-this-will-allow-the-user-to-link-to-an-existing-account-with-that-system-if-they-have-one-orwill-create-a-new-one-for-them--if-you-call-this-endpoint-with-a-test-jwt-we-will-simulateaccount-linking-by-redirecting-the-user-to-a-demo-permission-page-you-can-also-simulate-linking-or-unlinking-test-users-accounts-serverside-by-calling-thepost-v1userstestingusercurrenttransactable-systemsreference0simulateaccountlinkingfortestingendpoint-remember-that-not-all-systems-are-transactable-and-not-all-transactable-systems-requireaccount-linking--getting-and-setting-user-infowe-automatically-ingest-user-information-like-email-addresses-and-names-from-the-jwtauthorization-token-you-send-us--information-about-a-users-vehicle-like-their-license-plateneeds-to-be-set-through-our-api--we-require-this-in-order-for-the-user-to-transact-with-certainparking-operators-you-can-call-get-v1usersusercurrentreference0getuserinfo-to-get-all-theinformation-we-have-about-a-user-including-the-fields-we-deduce-from-their-jwt-and-those-thatyou-have-already-set-through-our-api-you-can-call-v1usersusercurrentupdate-vehiclereference0updateuservehicle-toupdate-the-vehicle-thats-associated-with-a-users-account-
  version: 1.0.0
host: api.coord.co
basePath: /v1/users
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /route:
    get:
      summary: Find a route.
      description: Find possible trips between two points using either or both of
        bike-share and transit.
      operationId: route_search
      x-api-path-slug: route-get
      parameters:
      - in: query
        name: access_key
        description: The API access key for the request
      - in: query
        name: bike_systems
        description: A comma-separated list of bike systems (as named in thebike share
          API)to use when routing
      - in: query
        name: destination_latitude
        description: The latitude of the destination point
      - in: query
        name: destination_longitude
        description: The longitude of the destination point
      - in: query
        name: modes
        description: The modes we can use in returned trip options
      - in: query
        name: num_options
        description: The maximum number of different trip options we should provide
          at once
      - in: query
        name: origin_latitude
        description: The latitude of the origin point
      - in: query
        name: origin_longitude
        description: The longitude of the origin point
      - in: query
        name: priority
        description: How we choose and sort the trip options
      - in: query
        name: time
        description: The time the trip starts or ends (depending on the `time_mode`
          flag), in ISO 8601format
      - in: query
        name: time_mode
        description: Whether `time` is the requested departure time or the requested
          arrival time
      responses:
        200:
          description: OK
      tags:
      - Routes
    post:
      summary: Get all toll rates corresponding to a single route
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
      operationId: get_cost_for_route
      x-api-path-slug: route-post
      parameters:
      - in: query
        name: access_key
        description: The API access key for the request
      - in: body
        name: route
        description: A description of the route being taken
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Route