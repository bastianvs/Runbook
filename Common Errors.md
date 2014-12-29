Common Errors
==============
* `IP address seems to have changed. Unable to listen on 'ns_1@'`

That message means that the software had a problem opening a port with that address. Couchbase server listens on all interfaces (0.0.0.0), and chooses which interface to use for its name (ns_1@IP) by determining which interface would lead out to external networks. This is determined by your routing table.

The general consensus is that these messages can occur in circumstances where the Erlang VM is having some kinds of trouble or may be due to any networking issue.
