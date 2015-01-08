Common Errors
==============

1.    `IP address seems to have changed. Unable to listen on 'ns_1@'`

That message means that the software had a problem opening a port with that address. Couchbase server listens on all interfaces (0.0.0.0), and chooses which interface to use for its name (ns_1@IP) by determining which interface would lead out to external networks. This is determined by your routing table.

The general consensus is that these messages can occur in circumstances where the Erlang VM is having some kinds of trouble or may be due to any networking issue.


2.     `Memecahed Crash`
 `[error_logger:error,2014-12-30T0:08:06.258,ns_1@10.42.131.20:error_logger<0.6.0>:ale_error_logger_handler:log_report:72] 
=========================CRASH REPORT========================= 
crasher: 
initial call: erlang:apply/2 
pid: <0.10739.5976> 
registered_name: [] 
exception error: no match of right hand side value {error,closed} `



http://www.couchbase.com/issues/browse/MB-9306

This is a known issue with Couchbase 2.2 and its is fixed in 2.5.x. I would suggest to upgrade your cluster to 2.5.x

`memcached: src/ep.cc:1119: void EventuallyPersistentStore::completeBGFetchMulti(uint16_t, std::vector<VBucketBGFetchItem*, std::allocator<VBucketBGFetchItem*> >&, hrtime_t): Assertion `v->isDirty()' failed.`
