# Features
- [documentation](https://aws.amazon.com/sqs/features/)

## Standard Queues

## FIFO Queues
- exactly once processing
- first in first out delivery

# Limitations

## FIFO Queues
- default:
    - 300 msgs/s
    - 3000 msg/second when batched (10 msg per operation)

# Pricing

## Standard
- 1st 1e6 request: free
- +1e6 request: $0.40 / 1e6 request

## FIFO
- 1st 1e6 request: free
- +1e6 request: $0.50 / 1e6 request
