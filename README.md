Docker compose file for setting up an EFK cluster
================================================

Basic docker compose setup that will serve Fluentd, Elasticsearch  and Kibana alongside with an example httpd service sending logs to the fluentd.
Fluentd (check fluentd/conf) gathers all logs from tcp socket input through docker logging driver, sends them to elasticsearch and kibana can visualize everything.

You can use this setup alongside with other docker containers or applications to gather all logs as a unified logging service. 

Example run
-------

Run with `docker-compose -f docker-compose.yml up`

You can access the httpd example at `http://localhost`. This will create apache access logs.
You can then visit kibana @ `http://localhost:5601`, set up a wildcard index for fluentd as `fluentd-*` and you can explore/filter all logs.


Feel free to edit current configuration for memory usage in Elasticsearch, exposed ports, volumes etc.

*Using elasticsearch,kibana v6.4.2 and fluentd v1.2*