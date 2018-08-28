{
  "info": {
    "name": "Azure Virtual Network API Routes List",
    "_postman_id": "fadc37bd-30e5-4409-a206-649a0ca035d1",
    "description": "Gets all routes in a route table.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "routes",
      "item": [
        {
          "id": "da057f05-7b77-48cd-adc6-857a3265cb99",
          "name": "Routes_List",
          "request": {
            "url": {
              "protocol": "http",
              "host": "management.azure.com",
              "path": [
                "subscriptions/:subscriptionId/resourceGroups/:resourceGroupName/providers/Microsoft.Network/routeTables/:routeTableName/routes"
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
            "description": "Gets all routes in a route table"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "4cacaee4-b9d7-4784-8816-aab13c058cef"
            }
          ]
        }
      ]
    }
  ]
}