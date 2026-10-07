# oss-vrp-replica-caller-c

Fourth caller in a replica harness built for an **authorized** bug-bounty report
(Google OSS VRP). It calls a reusable workflow **in our own account only**
(`ooriime/oss-vrp-replica-workflows`) and never calls, forks, or triggers anything in a
Google repository.

Its purpose is to measure one thing: the object key that the called workflow's `curl`
actually requests, when the caller supplies the bucket input. The `curl` in the replica
points at a listener bound to `127.0.0.1` on the runner, so nothing leaves it.
