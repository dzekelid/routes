{
  "info": {
    "name": "Azure Virtual Network API Route Filters Delete",
    "_postman_id": "9fff82fa-6b31-42ab-8cdf-02fff8d1f87b",
    "description": "Deletes the specified route filter.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Route Filters",
      "item": [
        {
          "id": "d5b1acd0-fe84-412d-b3fb-5a703f149705",
          "name": "RouteFilters_Delete",
          "request": {
            "url": {
              "protocol": "http",
              "host": "management.azure.com",
              "path": [
                "subscriptions/:subscriptionId/resourceGroups/:resourceGroupName/providers/Microsoft.Network/routeFilters/:routeFilterName"
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
            "method": "DELETE",
            "body": {
              "mode": "raw"
            },
            "description": "Deletes the specified route filter."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "7f55db0b-848a-438c-aee0-f40036177f4c"
            }
          ]
        }
      ]
    }
  ]
}