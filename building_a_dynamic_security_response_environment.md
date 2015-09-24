# BUILDING A DYNAMIC SECURITY RESPONSE ENVIRONMENT

The "security fortress" is dead

* Repsheet
	* keep the redis cache setup on the same box as the webapp
	* should something go wrong with downstreams, repsheet will fail open
* It's easier to get a new IP address than a new user account
* squirrel
	* hp.ipviking.com -> visualization of hacks, also provides reputation
	
go dependency management

```
export GOPATH=$(pwd)