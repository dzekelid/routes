{
  "info": {
    "name": "Azure Virtual Network API Route Filter Rules Get",
    "_postman_id": "8485c40f-cbf4-4895-bb69-75889c3e5eb9",
    "description": "Gets the specified rule from a route filter.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "route filter rules",
      "item": [
        {
          "id": "25d4fbf7-1f82-4530-96e1-9ea6035fd9c7",
          "name": "RouteFilterRules_Get",
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
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Gets the specified rule from a route filter"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "3280173b-d46a-4b04-b84a-5637cba636f9"
            }
          ]
        }
      ]
    }
  ]
}