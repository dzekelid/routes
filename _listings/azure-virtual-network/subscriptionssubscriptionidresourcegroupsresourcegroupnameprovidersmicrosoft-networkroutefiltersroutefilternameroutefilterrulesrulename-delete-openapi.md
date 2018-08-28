---
swagger: "2.0"
x-collection-name: Azure Virtual Network
x-complete: 0
info:
  title: Azure Virtual Network API Route Filter Rules Delete
  description: Deletes the specified rule from a route filter.
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
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetablesroutetablenameroutesroutename-delete
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
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetablesroutetablenameroutesroutename-get
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
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetablesroutetablenameroutesroutename-put
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
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetablesroutetablenameroutes-get
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
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeFilters/{routeFilterName}/routeFilterRules/{ruleName}
  : delete:
      summary: Route Filter Rules Delete
      description: Deletes the specified rule from a route filter.
      operationId: RouteFilterRules_Delete
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefilternameroutefilterrulesrulename-delete
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      - in: path
        name: ruleName
        description: The name of the rule
      responses:
        200:
          description: OK
      tags:
      - Route Filter Rules
    get:
      summary: Route Filter Rules Get
      description: Gets the specified rule from a route filter.
      operationId: RouteFilterRules_Get
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefilternameroutefilterrulesrulename-get
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      - in: path
        name: ruleName
        description: The name of the rule
      responses:
        200:
          description: OK
      tags:
      - Route Filter Rules
    put:
      summary: Route Filter Rules Create Or Update
      description: Creates or updates a route in the specified route filter.
      operationId: RouteFilterRules_CreateOrUpdate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefilternameroutefilterrulesrulename-put
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      - in: body
        name: routeFilterRuleParameters
        description: Parameters supplied to the create or update route filter rule
          operation
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: ruleName
        description: The name of the route filter rule
      responses:
        200:
          description: OK
      tags:
      - Route Filter Rules
    patch:
      summary: Route Filter Rules Update
      description: Updates a route in the specified route filter.
      operationId: RouteFilterRules_Update
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefilternameroutefilterrulesrulename-patch
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      - in: body
        name: routeFilterRuleParameters
        description: Parameters supplied to the update route filter rule operation
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: ruleName
        description: The name of the route filter rule
      responses:
        200:
          description: OK
      tags:
      - Route Filter Rules
  ? /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeFilters/{routeFilterName}/routeFilterRules
  : get:
      summary: Route Filter Rules List By Route Filter
      description: Gets all RouteFilterRules in a route filter.
      operationId: RouteFilterRules_ListByRouteFilter
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefilternameroutefilterrules-get
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      responses:
        200:
          description: OK
      tags:
      - Route Filter Rules
  /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeFilters/{routeFilterName}:
    delete:
      summary: Route Filters Delete
      description: Deletes the specified route filter.
      operationId: RouteFilters_Delete
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefiltername-delete
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      responses:
        200:
          description: OK
      tags:
      - Route Filters
    get:
      summary: Route Filters Get
      description: Gets the specified route filter.
      operationId: RouteFilters_Get
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefiltername-get
      parameters:
      - in: query
        name: $expand
        description: Expands referenced express route bgp peering resources
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      responses:
        200:
          description: OK
      tags:
      - Route Filters
    put:
      summary: Route Filters Create Or Update
      description: Creates or updates a route filter in a specified resource group.
      operationId: RouteFilters_CreateOrUpdate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefiltername-put
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      - in: body
        name: routeFilterParameters
        description: Parameters supplied to the create or update route filter operation
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Route Filters
    patch:
      summary: Route Filters Update
      description: Updates a route filter in a specified resource group.
      operationId: RouteFilters_Update
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefiltersroutefiltername-patch
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      - in: path
        name: routeFilterName
        description: The name of the route filter
      - in: body
        name: routeFilterParameters
        description: Parameters supplied to the update route filter operation
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Route Filters
  /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeFilters:
    get:
      summary: Route Filters List By Resource Group
      description: Gets all route filters in a resource group.
      operationId: RouteFilters_ListByResourceGroup
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutefilters-get
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      responses:
        200:
          description: OK
      tags:
      - Route Filters
  /subscriptions/{subscriptionId}/providers/Microsoft.Network/routeFilters:
    get:
      summary: Route Filters List
      description: Gets all route filters in a subscription.
      operationId: RouteFilters_List
      x-api-path-slug: subscriptionssubscriptionidprovidersmicrosoft-networkroutefilters-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Route Filters
  /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeTables/{routeTableName}:
    delete:
      summary: Route Tables Delete
      description: Deletes the specified route table.
      operationId: RouteTables_Delete
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetablesroutetablename-delete
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
      - Route Tables
    get:
      summary: Route Tables Get
      description: Gets the specified route table.
      operationId: RouteTables_Get
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetablesroutetablename-get
      parameters:
      - in: query
        name: $expand
        description: Expands referenced resources
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
      - Route Tables
    put:
      summary: Route Tables Create Or Update
      description: Create or updates a route table in a specified resource group.
      operationId: RouteTables_CreateOrUpdate
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetablesroutetablename-put
      parameters:
      - in: query
        name: No Name
      - in: body
        name: parameters
        description: Parameters supplied to the create or update route table operation
        schema:
          $ref: '#/definitions/holder'
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
      - Route Tables
  /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Network/routeTables:
    get:
      summary: Route Tables List
      description: Gets all route tables in a resource group.
      operationId: RouteTables_List
      x-api-path-slug: subscriptionssubscriptionidresourcegroupsresourcegroupnameprovidersmicrosoft-networkroutetables-get
      parameters:
      - in: query
        name: No Name
      - in: path
        name: resourceGroupName
        description: The name of the resource group
      responses:
        200:
          description: OK
      tags:
      - Route Tables
  /subscriptions/{subscriptionId}/providers/Microsoft.Network/routeTables:
    get:
      summary: Route Tables List All
      description: Gets all route tables in a subscription.
      operationId: RouteTables_ListAll
      x-api-path-slug: subscriptionssubscriptionidprovidersmicrosoft-networkroutetables-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Route Tables
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