### To add Data 

**URL:** 
```url
/api/add-data
``` 
**Payload:** 
```json
{
  "params":{
    "field_name_1": string,
    "field_name_2": integer
  },
  "modelName": "model_name" // example: user, invoice 
}
```


### To update Data

**URL:**
```url
/api/data/{id}
```
**Payload:**
```json
{
  "params":{
    "field_name_1": string,
    "field_name_2": integer
  },
  "modelName": "model_name" // example: user, invoice 
}
```


### Get dropdown data

**URL:**
```url
/api/dropdown/get
```
**Payload:**

If you have multiple dropdown fields, then you can add multiple objects as below.
```json
{
  "models": [
    {
      "model": "model_name_1", // user
      "label": "column_name" // name
    },
    {
      "model": "model_name_2", // course
      "label": "column_name" // course_name      
    }
  ]
}
```
In response, it will return 2 values for each option "value" and “label" . Check the response payload.



### Get table data

**URL:**
```url
/api/table/get
```
**Payload:**

If you have multiple dropdown fields, then you can add multiple objects as below.
```json
{
    "modelName": "user",
    "conditions": [ 
        [ 
            {
                "column": "email",
                "operator": "=",
                "value": "tawsif@coderslab.com.bd"
            }, // OR
            {
                "column": "name",
                "operator": "=",
                "value": "Tawsif Khan"
            }
        ], // AND
        [
            {
                "column": "email",
                "operator": "=",
                "value": "tawsif.online@gmail.com"
            }
        ]
    ],
    "columns": [
        "id",
        "name",
        "email"
    ],
    "actions": [
        'view',
        'edit'    // it will return buttons with button name and id
    ]
}
```