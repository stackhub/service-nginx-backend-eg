# Purpose

The sole purpose of this container is to provide a simple backend for a 
load balancer.  

# Usage

Production: *No*
StackEngine Only: *No*

## StackEngine Controller

To launch three (3) of these containers in a resource pool, copy and 
paste the contents of `stack.yml` in the Application Advanced Editor 
and launch it.

## CLI

This container is useful outside the StackEngine ecosystem.  To run it, it is 
necessary to ensure the internal port is 80:

`docker run -d -p :80 stackhub/nginx-backend-eg`

### Check it out

To see the container work, first run `docker ps` and note its external port.
This will probably be something like 32790 as seen int he example output below.  

`a138cc126fb1        stackhub/nginx-backend-eg   "/start.sh"         5 seconds ago       Up 4 seconds        443/tcp, 0.0.0.0:32790->80/tcp   hungry_leakey`

Then curl the address:

`curl http://localhost:32790`

and you will see as a response:

`<h1>a138cc126fb1</h1>`

By returning the container hash, you will easily be able to tell which backend
responded in a multicontainer situation such as using the 
[`servcie-haproxy`](http://github.com/stackhub-haproxy) 
for the StackEngine Container Application Center.

# License 

MIT