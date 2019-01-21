
### get_transcription_job

```python
client = boto3.client('transcribe')
job = client.get_transcription_job(TranscriptionJobName=jobId)
print(f"get_transcription_job {job}")
return job
```
