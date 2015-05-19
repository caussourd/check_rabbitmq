# Nagios plugin for rabbitMQ

* Check the number of connections (--action connections)

* Check the number of consumers in specific queues (--action consumers)

This plugin connects to the RabbitMQ management API.

This plugin is assuming that https is enabled for the rabbitMQ web access.

## Examples
It will check if myqueue has at least one consumer

`check_rabbitmq -H rabbitmq.mydomain --action consumers -u admin -p mypassword -Q myqueue -w 1:100 -c 1:1000`

It will check if the number of open connections is at least 11 (the default --action is connections)

`check_rabbitmq -H rabbitmq.mydomain  -u admin -p mypassword  -w 11:100 -c 11:1000`

For usage

`check_rabbitmq --help`

## Requirements
* pynagios (Installation: `pip install pynagios`)

## Acknowledgments
This plugin has been strongly inspired by https://github.com/kmcminn/rabbit-nagios