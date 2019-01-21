
## Effect

### send_email

```python
ses = boto3.client('ses')
source = FROM_EMAIL
subject = "Scribe Transcription Complete"
body = f"""
Hi,

Your transcription is now complete!
You can download a copy of the transcript at {url}

Thanks for transcribing with us and we hope to hear from you again soon!

Rock On!
The Scribe Team

ps. If you have any feedback, feel free to reply to us at this email. We are
constantly looking for ways to improve the serivce and welcome any and all
inquiries :)
"""
resp = ses.send_email(
    Source = source,
    Destination={
        "ToAddresses": [email]
    },
    Message = {
        "Subject": {
            "Charset": "UTF-8",
            "Data": subject,
        },
        "Body": {
            "Text": {
                "Charset": "UTF-8",
                "Data": body
            }
        }
    },
)
print(f"send_email, resp:{resp}")
return resp

```
