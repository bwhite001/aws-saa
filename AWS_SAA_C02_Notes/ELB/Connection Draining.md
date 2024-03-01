connection draining -  [[CLB]]
Deregestration delay - [[ALB]] and [[NLB]]

Time to complete inflight requests while the [[EC2]] instance is de registering or unhealthy
Stops sending new requests to [[EC2]] instance while deregistering.

default 300 seconds
Min = 1 second
Max = 1 hour

Can be disabled

