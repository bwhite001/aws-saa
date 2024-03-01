*Simple*
for single resources. If multiple values returned, random one is chosen by the client.
Health checks not possible

*Weighted*
assign weight to each records in % can be anything between 0 and 255
no need to sum up to 100%
DNS records must have same name and type
Can have health checks
Use case: Load balancing, testing new app versions


*Latency Based*
can have health checks 


*Fail Over* 
based on health check

*Geo location*
based on user location
can specify location based on continent, country or by US state
should create a default record if there is no match on location.
can have health checks

*Geo Proximity*
based on a bias. A bias can be co ordinates on map

Traffic flow - ui editor for decision trees

*Multi Value* - upto 8 records, can be associated with heaalth checks, not a substitute for ALB because it is a client side load balancing.





