Views Related Issues.
====================
1. Restarting View Manager.
----
`curl -X POST -u USER:PASSWORD http://localhost:8091/diag/eval -d 'rpc:eval_everywhere(erlang, apply, [fun () -> [exit(whereis(list_to_atom("capi_set_view_manager-" ++ B)), kill) || B <- ns_bucket:get_bucket_names(membase)] end, []]).'
`
