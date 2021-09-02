Example Voting App
=========

A simple distributed application running across multiple containers.

Architecture
-----

![Architecture diagram](architecture.png)

* A front-end web app in [Python](/vote) which lets you vote between two options
* A Redis queue which collects new votes
* A [.NET Core](/worker/src/Worker) or [Java](/worker/src/main) worker which consumes votes and stores them in…
* A Postgres database
* A [Node.js](/result) webapp which shows the results of the voting in real time

Notes
-----

The voting application only accepts one vote per client. It does not register votes if a vote has already been submitted from a client.

This isn't an example of a properly architected perfectly designed distributed app... it's just a simple 
example of the various types of pieces and languages you might see (queues, persistent data, etc), and how to 
deal with them in Docker at a basic level. 
