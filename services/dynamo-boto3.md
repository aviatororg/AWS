# Variables
- DYNAMO_TABLE: "editors"
- schema:
    - name: primary key, string
    - description: string
    - author: string

# Methods

## Properties

### scan

```python
dynamodb = boto3.resource('dynamodb')
table = dynamodb.Table(DYNAMO_TABLE)
author = "Bram Moolenaar"
response = table.scan(
    FilterExpression=Attr('author').eq(author)
)
items = response['Items']

```

## Mutations

### update_item

```python
dynamodb = boto3.resource('dynamodb')
table = dynamodb.Table(DYNAMO_TABLE)
key = "vim"
value = "Vim is a clone, with additions, of Bill Joy's vi text editor program for Unix."
resp = table.update_item(
    Key=key,
    UpdateExpression='SET description = :val',
    ExpressionAttributeValues={
        ':val': value
    }
)
```
