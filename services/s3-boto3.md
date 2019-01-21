

### get_object

```python
client = boto3.client('s3')
job_name = meta['TranscriptionJob']['TranscriptionJobName']
uri = meta['TranscriptionJob']['Transcript']['TranscriptFileUri']
resp = client.get_object(
    Bucket = BUCKET,
    Key = f"{job_name}.json"
)
print(f"get_transcript, resp: {resp['ETag']}")
res_json = json.loads(resp['Body'].read().decode('utf-8'))
return res_json
```

## Other

### generate_presigned_url

```python
s3 = boto3.client('s3')
url = s3.generate_presigned_url(
    ClientMethod='get_object',
    ExpiresIn=604800,
    Params={
        'Bucket': BUCKET,
        'Key': key,
    }
)
print(f"gen_presigned_url, key: {key}, url: {url}")
return url
```

## Mutate

### put_object

```python
client = boto3.client('s3')
s3_path = f"{BUCKET_PREFIX}/{key}.txt"
resp = client.put_object(
    Bucket = BUCKET,
    Key = s3_path,
    Body= transcript,
)
print(f"upload_transcript, resp: {resp['ETag']}")
return s3_path
```
