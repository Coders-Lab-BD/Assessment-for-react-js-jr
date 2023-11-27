## Task - 1

### To add Data 

**URL:** 
```url
POST /api/v1/models/store
```

**Payload:** 
```json
{
  "params": {
    "field_name_1": "string",
    "field_name_2": "integer"
  },
  "model": "model" // example: user, invoice 
}
```

### To update Data

**URL:**
```url
POST /api/v1/models/update/{id}
```

**Payload:**
```json
{
  "params": {
    "field_name_1": "string",
    "field_name_2": "integer"
  },
  "model": "model" // example: user, invoice 
}
```


### Get dropdown data

**URL:**
```url
POST /api/v1/models/dropdown
```
**Payload:**

If you have multiple dropdown fields, then you can add multiple objects as below.

```json
{
  "models": {
      "model": "model", // user
      "label": "column_name" // name
    },
}
```

In response, it will return 2 values for each option "value" and “label" . Check the response payload.

### Get table data

**URL:**
```url
POST /api/v1/models/get
```
**Payload:**

If you have multiple dropdown fields, then you can add multiple objects as below.
```json
{
    "model": "user",
    "columns": [
        "id",
        "name",
        "email"
    ],
    "actions": [
        "view",
        "edit"    // it will return buttons with button name and id
    ]
}
```
## Task - 2

You have to create a dynamic phone number input field and store them in an array of objects. For example:

```js
{
name: value,
numbers: [
    {
        number: "019..."
    },
    {
        number: "018..."
    } 
], 
password: value
}
```

 Users can increase or decrease the number of input field for phone numbers (upto 5). Finally, on submit, you have to display all the data in a card view on the right side of the form. Try to apply some styling when showing the submitted data.