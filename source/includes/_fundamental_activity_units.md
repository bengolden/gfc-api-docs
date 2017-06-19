
# Fundamental Activity Units

## Fundamental Activity Unit Creation

This API is to submit information about a fundamental activity unit that has been completed by a participant.

Only site administrators can access this API.

> Request:

```shell
curl -X "POST" "https://yoursite.cultivateforecasts.com/api/v1/fundamental_activity_units" \
  -H "Authorization: Bearer b95b4f848cd226e55b7a42f6a8e8669350730270f5a91d64b6c70328b0156d75" \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
	-d "{\"fundamental_activity_unit\":{\"membership_id\":45,\"metadata\": {\"foo\":\"bar\"}}}"
```

> Request body example:

```json
{
  "fundamental_activity_unit": {
    "membership_id": 45,
    "metadata": {
      "foo":"bar"
    }
  }
}
```


> Response:

```json
{
  "id": 6,
  "membership_id": 45,
  "metadata": {"foo":"bar"},
  "created_at": "2017-01-17T12:00:01.299Z",
  "updated_at": "2017-01-17T12:00:01.299Z"
}
```

### HTTP Request

`POST https://yoursite.cultivateforecasts.com/api/v1/fundamental_activity_units`


### Query Parameters

Parameter | Required? | Description
--------- | --------- | -----------
membership_id | Yes | The membership id of the user who performed the action
metadata | Yes | A JSON-formatted string describing the action taken by the user


### Attribute Descriptions

Parameter | Type | Description
--------- | ------- | -----------
id | integer | The id of the external prediction
membership_id | Yes | The membership id of the user who performed the action
metadata | Yes | A JSON-formatted string describing the action taken by the user
