# test
```
transfer_to_tip test2 "" "0.001 GOLOS" "" true
transfer_from_tip test2 "" "0.001 GOLOS" "" true
donate test2 test3 "1.234 GOLOS" {"app":"golos-io","version":1} true

begin_builder_transaction 
add_operation_to_builder_transaction 0 ["donate", {"from":"test2","to":"test3","amount":"1.000 GOLOS","memo":{"app":"golos-io","version":1,"target":{"author":1},"target2":{"author":1}}}]
sign_builder_transaction 0 true
```
