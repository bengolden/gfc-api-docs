# Aggregate Predictions

## Aggregate Predictions List

This endpoint provides a set of current consensus values for each question & potential answer. Includes a value calculated using each of the available aggregation methods.

Each aggregation method is a different formula/algorithm for taking a collection of individual forecast values and computing a consensus from them.

> Request:

```shell
curl "https://yoursite.cultivateforecasts.com/aggregation/api/v1/questions" \
  -H "Authorization: Bearer b95b4f848cd226e55b7a42f6a8e8669350730270f5a91d64b6c70328b0156d75"
```

> Response:

```json
{
  "questions": [
    {
      "id": 40,
      "name": "question-name-1",
      "answers": [
        {
          "id": 120,
          "name": "answer-name-3",
          "strategies": [
            {
              "method": "Mean",
              "value": 0.4
            },
            {
              "method": "WeightedMean",
              "value": 0.4
            },
            {
              "method": "Median",
              "value": 0.2
            },
            {
              "method": "WeightedMedian",
              "value": 0.2
            },
            {
              "method": "Voting",
              "value": 0.333333
            },
            {
              "method": "WeightedVoting",
              "value": 0.333333
            },
            {
              "method": "Logit",
              "value": 1.040042
            },
            {
              "method": "L2e",
              "value": 0.801018
            }
          ]
        },
        {
          "id": 119,
          "name": "answer-name-2",
          "strategies": [
            {
              "method": "Mean",
              "value": 0.333333
            },
            {
              "method": "WeightedMean",
              "value": 0.333333
            },
            {
              "method": "Median",
              "value": 0.2
            },
            {
              "method": "WeightedMedian",
              "value": 0.2
            },
            {
              "method": "Voting",
              "value": 0.333333
            },
            {
              "method": "WeightedVoting",
              "value": 0.333333},
            {
              "method": "Logit",
              "value": 0.956466
            },
            {
              "method": "L2e",
              "value": 0.633632
            }
          ]
        },
        {
          "id": 118,
          "name": "answer-name-1",
          "strategies": [
            {
              "method": "Mean",
              "value": 0.366667
            },
            {
              "method": "WeightedMean",
              "value": 0.366667
            },
            {
              "method": "Median",
              "value": 0.2
            },
            {
              "method": "WeightedMedian",
              "value": 0.2
            },
            {
              "method": "Voting",
              "value": 0.333333
            },
            {
              "method": "WeightedVoting",
              "value": 0.333333
            },
            {
              "method": "Logit",
              "value": 1.0
            },
            {
              "method": "L2e",
              "value": 0.717251
            }
          ]
        }
      ]
    }
  ]
}
```

### HTTP Request

`GET https://yoursite.cultivateforecasts.com/aggregation/api/v1/questions`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 0 | Pagination page number

### Attribute Descriptions

Parameter | Type | Description
--------- | ------- | -----------
questions.id | integer | The id of the question these consensus values are associated with
questions.name | string | The name of the question these consensus values are associated with
questions.answers.id | integer | The id of the answer these consensus values are associated with
questions.answers.name | string | The name of the answer these consensus values are associated with
questions.answers.strategies | array | An array of method/value pairs for the various consensus values
questions.answers.strategies.method | string | The name of the method used to compute this consensus value
questions.answers.strategies.value | float | The current consensus value for this method
