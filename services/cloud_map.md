# Resources
- https://aws.amazon.com/blogs/architecture/new-application-integration-with-aws-cloud-map-for-service-discovery/

# --- Scratch

```
ns_resp = CLIENT.create_private_dns_namespace(
    Name=namespace_name,
    Description=desc,
    Vpc=vpc_id,
)
op_id = ns_resp.get('OperationId')

# query
CLIENT.get_operation(OperationId=op_id)
```
