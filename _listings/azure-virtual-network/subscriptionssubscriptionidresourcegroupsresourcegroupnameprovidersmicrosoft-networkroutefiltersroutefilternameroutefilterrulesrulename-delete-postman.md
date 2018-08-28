{
  "info": {
    "name": "Azure Virtual Network API Route Filter Rules Delete",
    "_postman_id": "d0eaf53e-c672-46c6-9e70-8848240eefc6",
    "description": "Deletes the specified rule from a route filter.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "route filter rules",
      "item": [
        {
          "id": "8f743fe5-0ac4-4125-b0a7-58fb4f42e76d",
          "name": "RouteFilterRules_Delete",
          "request": {
            "url": {
              "protocol": "http",
              "host": "management.azure.com",
              "path": [
                "subscriptions/:subscriptionId/resourceGroups/:resourceGroupName/providers/Microsoft.Network/routeFilters/:routeFilterName/routeFilterRules/:ruleName"
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
                  "id": "ruleName",
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
            "method": "DELETE",
            "body": {
              "mode": "raw"
            },
            "description": "Deletes the specified rule from a route filter"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "2a0f1c7f-bd04-41a8-b6c9-93cb1d57bf82"
            }
          ]
        }
      ]
    }
  ]
}