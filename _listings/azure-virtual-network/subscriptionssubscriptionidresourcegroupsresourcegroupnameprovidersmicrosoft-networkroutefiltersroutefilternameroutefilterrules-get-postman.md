{
  "info": {
    "name": "Azure Virtual Network API Route Filter Rules List By Route Filter",
    "_postman_id": "8af5af6e-abf6-4db1-95b2-fdac4a45d49f",
    "description": "Gets all RouteFilterRules in a route filter.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "route filter rules",
      "item": [
        {
          "id": "288b4468-8c31-4f4c-9d36-b22ca554350d",
          "name": "RouteFilterRules_ListByRouteFilter",
          "request": {
            "url": {
              "protocol": "http",
              "host": "management.azure.com",
              "path": [
                "subscriptions/:subscriptionId/resourceGroups/:resourceGroupName/providers/Microsoft.Network/routeFilters/:routeFilterName/routeFilterRules"
              ],
              "query": [
                {
                  "key": "No Name",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "resourceGroupName",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "routeFilterName",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "subscriptionId",
                  "value": "subscriptionId",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Gets all RouteFilterRules in a route filter"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f2edf90e-31a4-4c46-87d5-1e46bec18dcb"
            }
          ]
        }
      ]
    }
  ]
}