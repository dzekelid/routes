---
swagger: "2.0"
x-collection-name: Azure Virtual Network
x-complete: 1
info:
  title: NetworkManagementClient
  description: the-microsoft-azure-network-management-api-provides-a-restful-set-of-web-services-that-interact-with-microsoft-azure-networks-service-to-manage-your-network-resources-the-api-has-entities-that-capture-the-relationship-between-an-end-user-and-the-microsoft-azure-networks-service
  version: 1.0.0
host: management.azure.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeTables/{routeTableName}/routes/{routeName}
  : delete:
      summary: Routes Delete
      description: Deletes the specified route from a route table.
      operationId: Routes_Delete
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoftnetworkroutetablesroutetablenameroutesroutename-delete
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeName
        description: The name of the route
      - in: path
        name: routeTableName
        description: The name of the route table
      responses:
        200:
          description: OK
      tags:
      - Routes
    get:
      summary: Routes Get
      description: Gets the specified route from a route table.
      operationId: Routes_Get
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoftnetworkroutetablesroutetablenameroutesroutename-get
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeName
        description: The name of the route
      - in: path
        name: routeTableName
        description: The name of the route table
      responses:
        200:
          description: OK
      tags:
      - Routes
    put:
      summary: Routes Create Or Update
      description: Creates or updates a route in the specified route table.
      operationId: Routes_CreateOrUpdate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoftnetworkroutetablesroutetablenameroutesroutename-put
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeName
        description: The name of the route
      - in: body
        name: routeParameters
        description: Parameters supplied to the create or update route operation
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: routeTableName
        description: The name of the route table
      responses:
        200:
          description: OK
      tags:
      - Routes
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeTables/{routeTableName}/routes
  : get:
      summary: Routes List
      description: Gets all routes in a route table.
      operationId: Routes_List
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoftnetworkroutetablesroutetablenameroutes-get
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeTableName
        description: The name of the route table
      responses:
        200:
          description: OK
      tags:
      - Routes
---