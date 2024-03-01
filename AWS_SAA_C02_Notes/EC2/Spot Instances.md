 short workloads, cheap, no availability when the max price is less than current spot price . batch jobs, data analysis, image processing, distributed work loads, with flexible start and end time
		1. 90 % discount compared to on demand.
		2. if spot price > max price, 
			1. stop 
			2. terminate
			3. apply spot block to prevent reclaiming (not reliable)
			
A sport request is used for raising  a spot instance .
Canceling a spot request does not terminate its instances.
First cancel a spot request then terminate any associated instances.
[[Spot Fleet]]