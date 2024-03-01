Application Load Balancer 


HTTP, HTTPS, Websocket (L7)
Load balancing to multiple [[EC2]] instances or within an instance

Under listeners one can setup rules with conditions and actions.
Conditions can include
1. path
2. host name
3. query string 
actions can include redirection to url, forwarding to target groups or providing a custom response

Redirecting is possible from https to http

used in microservice environment - Docker and Amazon ECS

Fixed host name - xxx.region.elb.amazonaws.com
Application servers don't see the ip of the client. Ip will be included within http header X-Forwarded-For
Port will be available in X-Forwarded-Port
Protocol will be in X-Forwarded-Proto

Target group refers to destination of Load Balancer
it can be
1. EC2 Instances
2. [[ECS]] tasks
3. Ip Address
4. [[Lambda]] Functions
5. Another application load balancer

One can't attach [[Elastic Ip]] to ALB



