---
name: Public Transport Victoria Timetable
x-slug: public-transport-victoria-timetable
description: The PTV Timetable API provides direct access to Public Transport Victoria&rsquo;s
  public transport timetable data. The API returns scheduled timetable, route and
  stop data for all metropolitan and regional train, tram and bus services in Victoria,
  including Night Network(Night Train and Night Tram data are included in metropolitan
  train and tram services data, respectively, whereas Night Bus is a separate route
  type). The API also returns real-time data for metropolitan train, tram and bus
  services (where this data is made available to PTV), as well as disruption information,
  stop facility information, and access to myki ticket outlet data.
image: ""
x-kinRank: "7"
x-alexaRank: "0"
tags: Routes
created: "2018-06-25"
modified: "2018-06-25"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/public-transport-victoria-timetable/apis.md
specificationVersion: "0.14"
apis:
- name: PTV Timetable API - Version 3 Get V3 Routes
  x-api-slug: ptv-timetable-api--version-3
  description: View route names and numbers for all routes.
  image: ""
  humanURL: https://www.ptv.vic.gov.au/about-ptv/data-and-reports/datasets/ptv-timetable-api/
  baseURL: https://timetableapi.ptv.vic.gov.au////v3/routes
  tags: Routes
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/public-transport-victoria-timetable/v3routes-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/public-transport-victoria-timetable/v3routes-get-openapi.md
- name: PTV Timetable API - Version 3 Get V3 Routes Route
  x-api-slug: ptv-timetable-api--version-3
  description: View route name and number for specific route id.
  image: ""
  humanURL: https://www.ptv.vic.gov.au/about-ptv/data-and-reports/datasets/ptv-timetable-api/
  baseURL: https://timetableapi.ptv.vic.gov.au////v3/routes/{route_id}
  tags: Routes,Route,Id
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/public-transport-victoria-timetable/v3routesroute-id-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/public-transport-victoria-timetable/v3routesroute-id-get-openapi.md
- name: PTV Timetable API - Version 3
  x-api-slug: ptv-timetable-api--version-3
  description: The PTV Timetable API provides direct access to Public Transport Victoria&rsquo;s
    public transport timetable data. The API returns scheduled timetable, route and
    stop data for all metropolitan and regional train, tram and bus services in Victoria,
    including Night Network(Night Train and Night Tram data are included in metropolitan
    train and tram services data, respectively, whereas Night Bus is a separate route
    type). The API also returns real-time data for metropolitan train, tram and bus
    services (where this data is made available to PTV), as well as disruption information,
    stop facility information, and access to myki ticket outlet data.
  image: ""
  humanURL: https://www.ptv.vic.gov.au/about-ptv/data-and-reports/datasets/ptv-timetable-api/
  baseURL: https://timetableapi.ptv.vic.gov.au//
  tags: Routes
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/routes/master/_listings/public-transport-victoria-timetable/openapi.md
x-common:
- type: x-website
  url: https://www.ptv.vic.gov.au/about-ptv/data-and-reports/datasets/ptv-timetable-api/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---