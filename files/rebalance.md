Rebalance
============
1. Increasse the no of connections for port 11209.
------
Actully we are being replaced with the exisiting value.

Find the exisiting value using cbstats.

`# /opt/couchbase/bin/cbstats localhost:11210 all | grep 11209
 curr_conns_on_port_11209: 6
 max_conns_on_port_11209: 1000`

`wget -O- --post-data='ns_config:update(fun ({{node, _, port_servers} = K, V}) -> {K, misc:rewrite_value("0.0.0.0:~B,0.0.0.0:~B:1000", "0.0.0.0:~B,0.0.0.0:~B:3000", V)}; (P) -> P end, "Sentinel").' http://admin:admin@127.0.0.1:8091/diag/eval`

`# sudo /etc/init.d/couchbase-server restart`

`# /opt/couchbase/bin/cbstats localhost:11210 all | grep 11209
 curr_conns_on_port_11209: 6
 max_conns_on_port_11209: 3000`
 

![alt text](https://github.com/bastianvs/Runbook/blob/master/images/rebalance.png "Logo Title Text 1")
