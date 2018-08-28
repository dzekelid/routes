---
swagger: "2.0"
x-collection-name: AWS Route 53
x-complete: 0
info:
  title: AWS Route 53 API List V P C Association Authorizations
  version: 1.0.0
  description: 'Gets a list of the VPCs that were created by other accounts and that
    can be associated with a specified hosted zone because you''ve submitted one or
    more CreateVPCAssociationAuthorization requests. Send a GET request to the /2013-04-01/hostedzone/hosted
    zone ID/authorizevpcassociation resource. The response to this request includes
    a VPCs element with a VPC child element for each VPC that can be associated with
    the hosted zone.Amazon Route 53 returns up to 50 VPCs per page. To return fewer
    VPCs per page, include the MaxResults parameter:             /2013-04-01/hostedzone/hosted
    zone ID/authorizevpcassociation?MaxItems=VPCs per page                     If
    the response includes a NextToken element, there are more VPCs to list. To get
    the next page of VPCs, submit another ListVPCAssociationAuthorizations request,
    and include the value of the NextToken element from the response in the NextToken
    request parameter:            /2013-04-01/hostedzone/hosted zone ID/authorizevpcassociation?MaxItems=VPCs
    per page&amp;NextToken='
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
  /2013-04-01/healthcheck:
    post:
      summary: Create Health Check
      description: Creates a new health check.To create a new health check, send a
        POST request to the/2013-04-01/healthcheck resource. The request body must
        include a documentwith a CreateHealthCheckRequest element. The response returns
        theCreateHealthCheckResponse element, containing the health check ID specifiedwhen
        adding health check to a resource record set. For information about adding
        health checksto resource record sets, see ResourceRecordSet:HealthCheckId
        in ChangeResourceRecordSets. If you are registering EC2 instances with an
        Elastic Load Balancing (ELB) loadbalancer, do not create Amazon Route 53 health
        checks for the EC2 instances. When you register anEC2 instance with a load
        balancer, you configure settings for an ELB health check, whichperforms a
        similar function to an Amazon Route 53 health check.You can associate health
        checks with failover resource record sets in a private hostedzone. Note the
        following:Amazon Route 53 health checkers are outside the VPC. To check the
        health of an endpointwithin a VPC by IP address, you must assign a public
        IP address to the instance in theVPC.You can configure a health checker to
        check the health of an external resource thatthe instance relies on, such
        as a database server.You can create a CloudWatch metric, associate an alarm
        with the metric, and then create ahealth check that is based on the state
        of the alarm. For example, you might create a CloudWatchmetric that checks
        the status of the Amazon EC2 StatusCheckFailed metric, add analarm to the
        metric, and then create a health check that is based on the state of thealarm.
        For information about creating CloudWatch metrics and alarms by using the
        CloudWatch console,see the Amazon CloudWatch User Guide.
      operationId: createhealthcheck
      x-api-path-slug: 20130401healthcheck-post
      parameters:
      - in: body
        name: CallerReference
        description: A unique string that identifies the request and that allows failedCreateHealthCheck
          requests to be retried without the risk of executing theoperation twice
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateHealthCheckRequest
        description: Root level tag for the CreateHealthCheckRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HealthCheckConfig
        description: A complex type that contains the response to a CreateHealthCheck
          request
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/healthcheck/HealthCheckId:
    delete:
      summary: Delete Health Check
      description: Deletes a health check. Send a DELETE request to the/2013-04-01/healthcheck/health
        check ID            resource.ImportantAmazon Route 53 does not prevent you
        from deleting a health check even if the health check isassociated with one
        or more resource record sets. If you delete a health check and you don'tupdate
        the associated resource record sets, the future status of the health check
        can't bepredicted and may change. This will affect the routing of DNS queries
        for your DNS failoverconfiguration. For more information, see Replacing and
        Deleting Health Checks in the Amazon Route 53 Developer Guide.
      operationId: deletehealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-delete
      parameters:
      - in: path
        name: HealthCheckId
        description: The ID of the health check that you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
    get:
      summary: Get Health Check
      description: Gets information about a specified health check. Send a GET request
        to the/2013-04-01/healthcheck/health check ID             resource. Formore
        information about using the console to perform this operation, see Amazon
        Route 53 Health Checks and DNS Failover in theAmazon Route 53 Developer Guide.
      operationId: gethealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-get
      parameters:
      - in: path
        name: HealthCheckId
        description: The identifier that Amazon Route 53 assigned to the health check
          when you created it
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
    post:
      summary: Update Health Check
      description: Updates an existing health check.Send a POST request to the /2013-04-01/healthcheck/health
        check ID             resource. Therequest body must include a document with
        an UpdateHealthCheckRequestelement. For more information about updating health
        checks, see Creating, Updating, and DeletingHealth Checks in the Amazon Route
        53 Developer Guide.
      operationId: updatehealthcheck
      x-api-path-slug: 20130401healthcheckhealthcheckid-post
      parameters:
      - in: body
        name: AlarmIdentifier
        description: A complex type that identifies the CloudWatch alarm that you
          want Amazon Route 53 health checkers touse to determine whether this health
          check is healthy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ChildHealthChecks
        description: A complex type that contains one ChildHealthCheck element for
          each healthcheck that you want to associate with a CALCULATED health check
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: EnableSNI
        description: Specify whether you want Amazon Route 53 to send the value ofFullyQualifiedDomainName
          to the endpoint in the client_hellomessage during TLS negotiation
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: FailureThreshold
        description: The number of consecutive health checks that an endpoint must
          pass or fail for Amazon Route 53 tochange the current status of the endpoint
          from unhealthy to healthy or vice versa
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: FullyQualifiedDomainName
        description: Amazon Route 53 behavior depends on whether you specify a value
          for IPAddress
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: HealthCheckId
        description: The ID for the health check for which you want detailed information
        type: string
      - in: body
        name: HealthCheckVersion
        description: A sequential counter that Amazon Route 53 sets to 1 when you
          create a health checkand increments by 1 each time you update settings for
          the health check
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HealthThreshold
        description: The number of child health checks that are associated with a
          CALCULATEDhealth that Amazon Route 53 must consider healthy for the CALCULATED
          health check to beconsidered healthy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: InsufficientDataHealthStatus
        description: 'When CloudWatch has insufficient data about the metric to determine
          the alarm state, the status that you want Amazon Route 53 to assign to the
          health check:                        Healthy: Amazon Route 53 considers
          the health check to be healthy'
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Inverted
        description: Specify whether you want Amazon Route 53 to invert the status
          of a health check, for example, toconsider a health check unhealthy when
          it otherwise would be considered healthy
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: IPAddress
        description: The IPv4 or IPv6 IP address for the endpoint that you want Amazon
          Route 53 to perform health checks on
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Port
        description: The port on the endpoint on which you want Amazon Route 53 to
          perform health checks
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Regions
        description: A complex type that contains one Region element for each region
          from which you wantAmazon Route 53 health checkers to check the specified
          endpoint
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: ResourcePath
        description: The path that you want Amazon Route 53 to request when performing
          health checks
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: SearchString
        description: If the value of Type is HTTP_STR_MATCH orHTTP_STR_MATCH, the
          string that you want Amazon Route 53 to search for in the responsebody from
          the specified resource
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: UpdateHealthCheckRequest
        description: Root level tag for the UpdateHealthCheckRequest parameters
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/healthcheck/HealthCheckId/lastfailurereason:
    get:
      summary: Get Health Check Last Failure Reason
      description: If you want to learn why a health check is currently failing or
        why it failed mostrecently (if at all), you can get the failure reason for
        the most recent failure. Send aGET request to the /Amazon Route 53 APIversion/healthcheck/health
        checkID/lastfailurereason resource.
      operationId: gethealthchecklastfailurereason
      x-api-path-slug: 20130401healthcheckhealthcheckidlastfailurereason-get
      parameters:
      - in: path
        name: HealthCheckId
        description: The ID for the health check for which you want the last failure
          reason
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/healthcheck?marker=Marker&amp;maxitems=MaxItems:
    get:
      summary: List Health Checks
      description: Retrieve a list of your health checks. Send a GET request to the/2013-04-01/healthcheck
        resource. The response to this request includes aHealthChecks element with
        zero or more HealthCheck child elements.By default, the list of health checks
        is displayed on a single page. You can control thelength of the page that
        is displayed by using the MaxItems parameter. You can usethe Marker parameter
        to control the health check that the list beginswith.For information about
        listing health checks using the Amazon Route 53 console, see Amazon Route
        53 Health Checks and DNS Failover.
      operationId: listhealthchecks
      x-api-path-slug: 20130401healthcheckmarkermarkerampmaxitemsmaxitems-get
      parameters:
      - in: path
        name: marker
        description: If the response to a ListHealthChecks is more than one page,
          marker is thehealth check ID for the first health check on the next page
          of results
        type: string
      responses:
        200:
          description: OK
      tags:
      - Checks
      - Health
  /2013-04-01/hostedzone:
    post:
      summary: Create Hosted Zone
      description: Creates a new public hosted zone, used to specify how the Domain
        Name System (DNS)routes traffic on the Internet for a domain, such as example.com,
        and its subdomains. ImportantPublic hosted zones can't be converted to a private
        hosted zone or vice versa.Instead, create a new hosted zone with the same
        name and create new resource recordsets.Send a POST request to the /2013-04-01/hostedzone
        resource. The request body must include a documentwith a CreateHostedZoneRequest
        element. The response returns theCreateHostedZoneResponse element containing
        metadata about the hostedzone.Fore more information about charges for hosted
        zones, see Amazon Route 53 Pricing.Note the following:You can't create a hosted
        zone for a top-level domain (TLD).Amazon Route 53 automatically creates a
        default SOA record and four NS records for the zone.For more information about
        SOA and NS records, see NS and SOA Records that Amazon Route 53 Creates for
        a Hosted Zone in the Amazon Route 53 Developer Guide.If your domain is registered
        with a registrar other than Amazon Route 53, you must update thename servers
        with your registrar to make Amazon Route 53 your DNS service. For more information,
        seeConfiguring Amazon Route 53 as your DNSService in the Amazon Route 53 Developer's
        Guide.After creating a zone, its initial status is PENDING. This means that
        itis not yet available on all DNS servers. The status of the zone changes
        to INSYNCwhen the NS and SOA records are available on all Amazon Route 53
        DNS servers. When trying to create a hosted zone using a reusable delegation
        set, specify anoptional DelegationSetId, and Amazon Route 53 would assign
        those 4 NS records for the zone, instead ofallotting a new one.
      operationId: createhostedzone
      x-api-path-slug: 20130401hostedzone-post
      parameters:
      - in: body
        name: CallerReference
        description: A unique string that identifies the request and that allows failedCreateHostedZone
          requests to be retried without the risk of executing theoperation twice
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateHostedZoneRequest
        description: Root level tag for the CreateHostedZoneRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Default
        description: None
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: DelegationSetId
        description: If you want to associate a reusable delegation set with this
          hosted zone, the ID thatAmazon Route 53 assigned to the reusable delegation
          set when you created it
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneConfig
        description: (Optional) A complex type that contains an optional comment about
          your hosted zone
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Name
        description: The name of the domain
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: Parent
        description: CreatedHostedZoneRequest
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: VPC
        description: The VPC that you want your hosted zone to be associated with
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
  /2013-04-01/hostedzone&amp;delegationsetid=DelegationSetId?marker=Marker&amp;maxitems=MaxItems:
    get:
      summary: List Hosted Zones
      description: 'To retrieve a list of your public and private hosted zones, send
        a GETrequest to the /2013-04-01/hostedzone resource. The response to this
        requestincludes a HostedZones child element for each hosted zone created by
        the currentAWS account.Amazon Route 53 returns a maximum of 100 items in each
        response. If you have a lot of hostedzones, you can use the maxitems parameter
        to list them in groups of up to 100.The response includes four values that
        help navigate from one group of maxitemshosted zones to the next:                  MaxItems
        is the value specified for the maxitems parameterin the request that produced
        the current response.If the value of IsTruncated in the response is true,
        there are morehosted zones associated with the current AWS account.                   NextMarker
        is the hosted zone ID of the next hosted zone that isassociated with the current
        AWS account. If you want to list more hosted zones, makeanother call to ListHostedZones,
        and specify the value of theNextMarker element in the marker parameter. If
        IsTruncated is false, the NextMarker element isomitted from the response.If
        you''re making the second or subsequent call to ListHostedZones, theMarker
        element matches the value that you specified in themarker parameter in the
        previous request.'
      operationId: listhostedzones
      x-api-path-slug: 20130401hostedzoneampdelegationsetiddelegationsetidmarkermarkerampmaxitemsmaxitems-get
      parameters:
      - in: path
        name: delegationsetid
        description: If youre using reusable delegation sets and you want to list
          all of the hosted zones that are associated with a reusable delegation set,
          specify the ID of that reusable delegation set
        type: string
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
  /2013-04-01/hostedzone/Id:
    delete:
      summary: Delete Hosted Zone
      description: Deletes a hosted zone. Send a DELETE request to the /Amazon Route
        53API version/hostedzone/hosted zone ID             resource.ImportantDelete
        a hosted zone only if there are no resource record sets other than the defaultSOA
        record and NS resource record sets. If the hosted zone contains other resource
        recordsets, delete them before deleting the hosted zone. If you try to delete
        a hosted zone thatcontains other resource record sets, Amazon Route 53 denies
        your request with aHostedZoneNotEmpty error. For information about deleting
        records from yourhosted zone, see ChangeResourceRecordSets.
      operationId: deletehostedzone
      x-api-path-slug: 20130401hostedzoneid-delete
      parameters:
      - in: path
        name: Id
        description: The ID of the hosted zone you want to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
    get:
      summary: Get Hosted Zone
      description: Retrieves the delegation set for a hosted zone, including the four
        name serversassigned to the hosted zone. Send a GET request to the /Amazon
        Route 53 APIversion/hostedzone/hosted zone ID             resource.
      operationId: gethostedzone
      x-api-path-slug: 20130401hostedzoneid-get
      parameters:
      - in: path
        name: Id
        description: The ID of the hosted zone for which you want to get a list of
          the name servers in thedelegation set
        type: string
      responses:
        200:
          description: OK
      tags:
      - Hosted Zones
  /2013-04-01/hostedzone/Id/authorizevpcassociation&amp;maxresults=MaxResults?nexttoken=NextToken:
    get:
      summary: List V P C Association Authorizations
      description: 'Gets a list of the VPCs that were created by other accounts and
        that can be associated with a specified hosted zone because you''ve submitted
        one or more CreateVPCAssociationAuthorization requests. Send a GET request
        to the /2013-04-01/hostedzone/hosted zone ID/authorizevpcassociation resource.
        The response to this request includes a VPCs element with a VPC child element
        for each VPC that can be associated with the hosted zone.Amazon Route 53 returns
        up to 50 VPCs per page. To return fewer VPCs per page, include the MaxResults
        parameter:             /2013-04-01/hostedzone/hosted zone ID/authorizevpcassociation?MaxItems=VPCs
        per page                     If the response includes a NextToken element,
        there are more VPCs to list. To get the next page of VPCs, submit another
        ListVPCAssociationAuthorizations request, and include the value of the NextToken
        element from the response in the NextToken request parameter:            /2013-04-01/hostedzone/hosted
        zone ID/authorizevpcassociation?MaxItems=VPCs per page&amp;NextToken='
      operationId: listvpcassociationauthorizations
      x-api-path-slug: 20130401hostedzoneidauthorizevpcassociationampmaxresultsmaxresultsnexttokennexttoken-get
      parameters:
      - in: path
        name: Id
        description: The ID of the hosted zone for which you want a list of VPCs that
          can be associated with the hosted zone
        type: string
      responses:
        200:
          description: OK
      tags:
      - VPC
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