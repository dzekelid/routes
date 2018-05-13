{
  "info": {
    "name": "Azure Virtual Network API Routes Get",
    "_postman_id": "d782b376-84c2-470b-ab59-15fcafbcd446",
    "description": "Gets the specified route from a route table.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "routes",
      "item": [
        {
          "id": "20285866-138a-4411-824f-73504a38a8be",
          "name": "Routes_Get",
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
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Gets the specified route from a route table"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "ebfe8fdf-3562-4baf-a46f-ff5be387e32c"
            }
          ]
        }
      ]
    }
  ]
}