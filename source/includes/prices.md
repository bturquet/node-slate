# Prices API

Welcome to the Prices API! Please read before the introduction and authentication process.

The OPM is Julien D.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

## Items prices of a department

```bash
curl "/api/v3/stores/{storeId}/departments/{departmentId}/items/prices"
  -H "Authorization: API KEY"
```

> The above command returns JSON structured like this:

```json
{
  "id": 0,
  "name": "string",
  "sub_departments": [
    {
      "families": [
        {
          "id": 0,
          "models": [
            {
              "brand": "string",
              "id": 0,
              "items": [
                {
                  "item": {
                    "department": {
                      "id": 0,
                      "name": "string"
                    },
                    "eans": [
                      "string"
                    ],
                    "family": {
                      "id": 0,
                      "name": "string"
                    },
                    "id": 0,
                    "is_rfid": true,
                    "model": {
                      "brand": "string",
                      "id": 0,
                      "name": "string"
                    },
                    "size": "string",
                    "sub_department": {
                      "id": 0,
                      "name": "string"
                    },
                    "universe": {
                      "id": 0,
                      "name": "string"
                    }
                  },
                  "price": {
                    "currency": "string",
                    "price_excluding_tax": 0,
                    "price_type": "string",
                    "prmp": 0,
                    "sale_price": 0,
                    "start_date": "2017-10-11T08:55:51.298Z",
                    "stop_date": "2017-10-11T08:55:51.298Z",
                    "strikeout_price": 0
                  }
                }
              ],
              "name": "string"
            }
          ],
          "name": "string"
        }
      ],
      "id": 0,
      "name": "string"
    }
  ]
}
```

Get the price information of every item of a department.
### HTTP Request

`GET /api/v3/stores/{storeId}/departments/{departmentId}/items/prices`

### Query Parameters

Parameter | Value | Description | Parameter Type | Data Type
--------- | ------- | ----------- | ----------- | -----------
Accept-Language | fr-FR | The specific language for labels {format: xx-XX} (ex: fr-FR) | header | undefined
storeId | (required) | Store number, example : 648 | path | integer
departmentId | (required) | Department number, example : 123123 | path | integer
include | Provide multiple values in new lines. | Possible values are : universe.name, department.name, sub_department.name, family.name, model.brand, model.name, item.label, item.rfid, item.eans, item.parents, price_infos.price_type, price_infos.strikeout_price, price_infos.price_excluding_tax, price_infos.prmp, price_infos.start_date, price_infos.stop_date | query | Array[string]

### Error Codes

HTTP Status Code | Reason | Response Model | Headers
---------- | ------- | ------- | -------
401 | Unauthorized -- Your API key is wrong | ------- | -------
403 | Forbidden -- The Item requested is hidden for administrators only | ------- | -------
404 | Not Found -- The specified Item could not be found | ------- | -------

## Items prices of a sub-department
Get the price information of every item of a sub-department

## Items prices of a family
Get the price information of every item of a family

## Items prices of a model
Get a model by its external code, including every item with its price information

## Specific Item price information
Get a specific item by its external reference with its price information
