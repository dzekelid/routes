{
  "info": {
    "name": "Azure Virtual Network API Routes Delete",
    "_postman_id": "5e7dc56c-f3c0-44b5-b205-8a80845bcaac",
    "description": "Deletes the specified route from a route table.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "routes",
      "item": [
        {
          "id": "0a3fe361-446c-449d-8511-271cf078adfb",
          "name": "Routes_Delete",
          "request": {
            "url": {
              "protocol": "http",
              "host": "management.azure.com",
              "path": [
                "subscriptions/:subscriptionId/resourceGroups/:resourceGroupName/providers/Microsoft.Network/routeTables/:routeTableName/routes/:routeName"
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
                  "id": "routeName",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "routeTableName",
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
            "description": "Deletes the specified route from a route table"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "13d4b66a-cc5a-4bfd-bec5-be2dfdb8b174"
            }
          ]
        }
      ]
    }
  ]
}