
# Why Replication?

## So let's understand why do we need a copy of a database server.

### High Availability:
- Let's say something happens to a master server, a problem with the hardware suppose, the server will go down, right?
- Hence, having a copy of the master server (database in that server) on to another server or servers, we can reduce the downtime.
- If, let's say, I have 10 users using my stuff, and for some reason my stuff could not be available to them at the time they need it. I don't want them to get impacted because of my problem. So what I do is to ask them to take the same stuff from another location. The other location/locations also provide them the same thing. Hence, I created the other location/locations as a backup in case my main location has some problem.

### Load Balancing:
- In general, load balancing is the process where we distribute the network traffic among multiple servers so that no single server gets overwhelmed with all the traffic which could result in a failure!
- Let's say there's only one way that leads to a sea. During summers, everyone will take that route to head towards the sea. What's gonna happen? A lot of traffic? Delay? So, in order to solve this problem, we can carve out another route towards the sea so that the people can now take the other route as well. This will reduce the traffic, and hence the delay.
- If the server has a lot of load on it, let's say, more data is being read from the server than  it is being written. In that case, we can have a slave server which will act as a replica for the master server which will handle the read queries from the users, while the master server will take care of all the write operations (Load Balancer forwards the read request to the slave server, and 'inserts, updates, deletes for example' to the master server).

### Disaster Recovery: 
- If something happens to a master server, if for some reason it crashes or corrupted, we always have a copy so that we don't lose the data, which is the most crucial thing!
- Like we like to keep a spare medicine in case we lose the first one (Because medicine is crucial)! :-D
