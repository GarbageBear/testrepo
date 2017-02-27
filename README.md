## Test repository for performance testing

### Outline
Create a basic performance testing framework

#### Hardware
- 4 5610s in development - same machines (replace with modern towers)
- Then they sit in a server room - run windows server 2016 (docker)

#### Software

fme installation builds 
- beta builds at least
- rev builds if possible

testsuite / master performance source data
- accessible on a shared drive 
- copied locally for performance

test harness 
- YAML harness config for testsuite (replace) -> saved to drive -> python compare and analyze
- YAML and new Python harness + FME command to dump stats / times -> JSON files save to shared drive

shared log output location
- drive/dropbox account
- files for logstash

webhooks setup to notify on
- first failure
- test completion
- test harness errors

Docker to Github trigger URLs / token
https://registry.hub.docker.com/u/garbagebear/testrepo/trigger/512bfda0-a5d7-4620-8cb7-ac07eebe71f9/

Docker Machine setup
--------------------
Docker Kitematic UI - get the ELK server and Python Windows server setup
Docker Engine - to run this
Docker Compose - YAML configuration - paths and config for data, tests, harness, servers

ELK Server
----------
ElasticSearch - store queryable result
Logstash - capture docker input as JSON -> ElasticSearch
Kibana - Dashboard / report on results

Multiple Nodes
--------------
Docker Swarm - Distribition / orchestration of 4 machines
