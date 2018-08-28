---
swagger: "2.0"
x-collection-name: AWS Route 53
x-complete: 0
info:
  title: AWS Route 53 API List Geo Locations
  version: 1.0.0
  description: Retrieves a list of supported geo locations. Send a GET request to
    the/2013-04-01/geolocations resource. The response to this request includes aGeoLocationDetailsList
    element for each location that Amazon Route 53 supports.Countries are listed first,
    and continents are listed last. If Amazon Route 53 supportssubdivisions for a
    country (for example, states or provinces), the subdivisions for thatcountry are
    listed in alphabetical order immediately after the corresponding country.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /2013-04-01/change/Id:
    get:
      summary: Get Change
      description: 'Returns the current status of a change batch request. The status
        is one of thefollowing values:                  PENDING indicates that the
        changes in this request have not replicatedto all Amazon Route 53 DNS servers.
        This is the initial status of all change batchrequests.                  INSYNC
        indicates that the changes have replicated to all Amazon Route 53 DNSservers.'
      operationId: getchange
      x-api-path-slug: 20130401changeid-get
      parameters:
      - in: path
        name: Id
        description: The ID of the change batch request
        type: string
      responses:
        200:
          description: OK
      tags:
      - Changes
  /2013-04-01/checkeripranges:
    get:
      summary: Get Checker Ip Ranges
      description: GetCheckerIpRanges still works, but we recommend that you download
        ip-ranges.json, which includes IP address ranges for all AWS services. For
        more information, see IP Address Ranges of Amazon Route 53 Servers in the
        Amazon Route 53 Developer Guide.
      operationId: getcheckeripranges
      x-api-path-slug: 20130401checkeripranges-get
      responses:
        200:
          description: OK
      tags:
      - IP Ranges
  /2013-04-01/delegationset?marker=Marker&amp;maxitems=MaxItems:
    get:
      summary: List Reusable Delegation Sets
      description: To retrieve a list of your reusable delegation sets, send a GET
        request tothe /2013-04-01/delegationset resource. The response to this request
        includes aDelegationSets element with zero, one, or multiple DelegationSetchild
        elements. By default, the list of delegation sets is displayed on a single
        page. You cancontrol the length of the page that is displayed by using the
        MaxItems parameter.You can use the Marker parameter to control the delegation
        set that the listbegins with. Note Amazon Route 53 returns a maximum of 100
        items. If you set MaxItems to a value greater than100, Amazon Route 53 returns
        only the first 100.
      operationId: listreusabledelegationsets
      x-api-path-slug: 20130401delegationsetmarkermarkerampmaxitemsmaxitems-get
      parameters:
      - in: path
        name: marker
        description: If youre making the second or subsequent call toListReusableDelegationSets,
          the Marker element matches the valuethat you specified in the marker parameter
          in the previous request
        type: string
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
  ? /2013-04-01/geolocations&amp;maxitems=MaxItems?startcontinentcode=StartContinentCode&amp;startcountrycode=StartCountryCode&amp;startsubdivisioncode=StartSubdivisionCode
  : get:
      summary: List Geo Locations
      description: Retrieves a list of supported geo locations. Send a GET request
        to the/2013-04-01/geolocations resource. The response to this request includes
        aGeoLocationDetailsList element for each location that Amazon Route 53 supports.Countries
        are listed first, and continents are listed last. If Amazon Route 53 supportssubdivisions
        for a country (for example, states or provinces), the subdivisions for thatcountry
        are listed in alphabetical order immediately after the corresponding country.
      operationId: listgeolocations
      x-api-path-slug: 20130401geolocationsampmaxitemsmaxitemsstartcontinentcodestartcontinentcodeampstartcountrycodestartcountrycodeampstartsubdivisioncodestartsubdivisioncode-get
      parameters:
      - in: path
        name: maxitems
        description: (Optional) The maximum number of geolocations to be included
          in the response body forthis request
        type: string
      responses:
        200:
          description: OK
      tags:
      - Locations
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