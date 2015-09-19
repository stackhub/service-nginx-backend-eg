# Purpose

The sole purpose of this container is to provide a simple backend for a 
load balancer.  

# Usage

# StackEngine Controller

To launch three (3) of these containers in a resource pool, copy and 
paste the contents of `stack.yml` in the Application Advanced Editor 
and launch it.

# CLI

This container is useful outside the StackEngine ecosystem.  To run it, it is 
necessary to ensure the internal port is 80:

`docker run -d -p :80 stackhub/service-nginx-example1`

# License 

MIT