5 Minute BELK Stack
===================

## Intro
A set of Cloudformation scripts that make it easy to stand up ElasticSearch, Logstash and Kibana with the plan of feeding them metrics via Beats. 

The platform consists of Docker containers running on Mesos AWS EC2 slaves scheduled by Marathon and Chronos. 

## Setting Up Your Stack
Start by creating a VPC with internet gateway, one subnet (with 0.0.0.0/0 route to IGW), EC2 key, and one seccurity group that allows 22 (or port of your choice), 2151 and 8181. 

Next, create the first stack using the `zookeeper.json` file. 

Follow that up by adding `mesos-master.json` and `mesos-slave.json` into your Cloudformation S3 bucket. Take note of the location of both of these as you'll need the for the next step. 

Now run Cloudformation for the `mesos.json` file. 
