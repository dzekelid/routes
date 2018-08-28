---
name: Flowroute
x-slug: flowroute
description: Flowroute is the leading provider of cloud-based communications and is
  based in Seattle, Washington.
image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28795-developer-flowroute-com.jpg
x-kinRank: "7"
x-alexaRank: "235018"
tags: Routes
created: "2018-08-28"
modified: "2018-08-28"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/flowroute/apis.md
specificationVersion: "0.14"
apis:
- name: Flowroute APIs - List Inbound Routes
  x-api-slug: v2routes-get
  description: Returns a list of your inbound routes. From the list, you can then
    select routes to use as the primary and failover routes for a phone number, which
    you can do via "Update Primary Voice Route for a Phone Number" and "Update Failover
    Voice Route for a Phone Number".
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28795-developer-flowroute-com.jpg
  humanURL: http://developer.flowroute.com
  baseURL: https:////
  tags: Telecommunications, ISP, Technology, Messages
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/flowroute/v2routes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/flowroute/v2routes-get-openapi.md
- name: Flowroute APIs - Create an Inbound Route
  x-api-slug: v2routes-post
  description: Creates a new inbound route which can then be associated with phone
    numbers. Please see "List Inbound Routes" to review the route values that you
    can associate with your Flowroute phone numbers.
  image: http://kinlane-productions.s3.amazonaws.com/screen-capture-api/28795-developer-flowroute-com.jpg
  humanURL: http://developer.flowroute.com
  baseURL: https:////
  tags: Telecommunications, ISP, Technology, Messages
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/flowroute/v2routes-post-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/flowroute/v2routes-post-openapi.md
x-common:
- type: x-github
  url: https://github.com/flowroute
- type: x-openapi
  url: https://raw.githubusercontent.com/flowroute/flowroute-sdk-v3-dot-net/master/swagger_specs/Flowroute_API_01172018.json
- type: x-api-gallery
  url: http://evrythng.api.gallery.streamdata.io
- type: x-crunchbase
  url: https://crunchbase.com/organization/flowroute
- type: x-email
  url: legal@flowroute.com
- type: x-twitter
  url: https://twitter.com/flowroute
- type: x-website
  url: http://developer.flowroute.com
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---