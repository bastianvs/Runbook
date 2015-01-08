Gloassary
============

Transparent Huge Pages		
		
		
Data Change Protocol	"- Lower Replication Latency: for XDCR and Views

- Faster Rebalance: will provide ability to rollback and catchup incrementally under failover.

- Views with (stale=false):ability to maintain views for a given mutation with stale=false with much lower latency."	http://docs.couchbase.com/admin/admin/Concepts/dcp.html
		
		
		
		
		
		
		
		
		
	TAP referred to the interface between the nodes in the cluster.  Developers and users don't normally use this.  The internal system uses TAP to replicate and rebalance data onto other nodes.  You can think of TAP as the real-time stream out of all the changes happening to a node, that stream is read by other nodes for replication and rebalancing purposes. 	http://docs.couchbase.com/admin/admin/Concepts/concepts-TAP.html
		
		
		
		
		
		
		
		
		
		
