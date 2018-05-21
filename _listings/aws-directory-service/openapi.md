---
swagger: "2.0"
x-collection-name: AWS Directory Service
x-complete: 1
info:
  title: AWS Directory Service API
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=AddIpRoutes:
    get:
      summary: Add Ip Routes
      description: If the DNS server for your on-premises domain uses a publicly addressable
        IP address, you must add a CIDR address block to correctly route traffic to
        and from your Microsoft AD on Amazon Web Services.
      operationId: addIpRoutes
      x-api-path-slug: actionaddiproutes-get
      parameters:
      - in: query
        name: DirectoryId
        description: Identifier (ID) of the directory to which to add the address
          block
        type: string
      - in: query
        name: IpRoutes
        description: IP address blocks, using CIDR format, of the traffic to route
        type: string
      - in: query
        name: UpdateSecurityGroupForDirectoryControllers
        description: 'If set to true, updates the inbound and outbound rules of the
          security group that has the description: AWS created security group for
          directory ID directory controllers'
        type: string
      responses:
        200:
          description: OK
      tags:
      - IP Address Routes
  /?Action=ListIpRoutes:
    get:
      summary: List Ip Routes
      description: Lists the address blocks that you have added to a directory.
      operationId: listIpRoutes
      x-api-path-slug: actionlistiproutes-get
      parameters:
      - in: query
        name: DirectoryId
        description: Identifier (ID) of the directory for which you want to retrieve
          the IP addresses
        type: string
      - in: query
        name: Limit
        description: Maximum number of items to return
        type: string
      - in: query
        name: NextToken
        description: The ListIpRoutes
        type: string
      responses:
        200:
          description: OK
      tags:
      - IP Address Routes
  /?Action=RemoveIpRoutes:
    get:
      summary: Remove Ip Routes
      description: Removes IP address blocks from a directory.
      operationId: removeIpRoutes
      x-api-path-slug: actionremoveiproutes-get
      parameters:
      - in: query
        name: CidrIps
        description: IP address blocks that you want to remove
        type: string
      - in: query
        name: DirectoryId
        description: Identifier (ID) of the directory from which you want to remove
          the IP addresses
        type: string
      responses:
        200:
          description: OK
      tags:
      - IP Address Routes
---