## Infrastructure for Applications 

Application is the backend that we write, infrastructure on the other hand consists of 
- storage 
- communication 
- computation
  
We would like the infra to always scale horizontally but a single Database instance will always become a bottleneck and we will run out of gas in the storage level infra.

## Fault Tolerant System

Big scale turns those problems which we don't really have to worry about into problems that we have to deal with every day.

But what do we really mean by Fault Tolerant system 

- Availability
	- Despite the failure the system is still up and running 
	- Maybe if we have replicated server, maybe one server fails and the other one is still available.
- Recover-ability
	- The ability of get up and going again 
	- Maybe write the state into the disk on a failure 
	- But after it has been repaired it works as nothing has happened
- Consistency
	- Lets say there are two servers of cache
	- Update goes to server 1 and the update is not communicated to server 2 
	- Now server 2 has stale data
		- #### Strong consistency
			- if there is one change in one server replicate the change to all the servers or maybe sort by update time in both the cases its very expensive operation
		- #### Weak consistency
			- since the server consistent replication is expensive
			- Most people use weak consistent systems which has no guarantee of consistent data
			- There are a lot of real world papers on how to structure weak consistency so that we ensure data consistency.

Tools we use for managing these fault tolerant systems are 
- Non Volatile storage 
- store the latest state of the failure in the Database
- Replication
- Key problem where we have any replicated system, both of the instances will drift away from each other and stop being replicated system.
## Map Reduce



