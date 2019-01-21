
# Performance
- docs: https://docs.aws.amazon.com/efs/latest/ug/performance.html

- two modes: general and provisioned
- general
    - description:  latency-sensitive use cases
    - throughput: 10+GB/s
    - usecase:  latency-sensitive use cases, like web serving environments, content management systems, home directories, and general file serving
- provisioned:
    - description: File systems in the Max I/O mode can scale to higher levels of aggregate throughput and operations per second with a tradeoff of slightly higher latencies for file operations
    - throughput: 2GB/s
    - usecase: Highly parallelized applications and workloads, such as big data analysis, media processing, and genomics analysis, can benefit from this mode.

# Use Cases

# --- FAQ

### EFS with lots of small files
- not ideal
- if you have to
    - redis
    - serve out of cloudfront
