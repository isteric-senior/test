# test HF 24
```
create_asset cyberfounder "100000.000 TOKENCHIK" true
create_asset cyberfounder "1.0 TOKENCHIK.CENT" true
create_asset cyberfounder "1.0 GOLOS.CENT" true
create_asset cyberfounder "1.0 LONGLONGTOOLONGTICKER" true

transfer cyberfounder test "0.001 TOKENCHIK" "" true
transfer cyberfounder test "1.0 TOKENCHIK.CENT" "" true
```

# test HF 23
```
transfer_to_tip test2 "" "0.001 GOLOS" "" true
transfer_from_tip test2 "" "0.001 GOLOS" "" true
donate test2 test3 "1.234 GOLOS" {"app":"golos-io","version":1} true

begin_builder_transaction 
add_operation_to_builder_transaction 0 ["donate", {"from":"test2","to":"test3","amount":"1.000 GOLOS","memo":{"app":"golos-io","version":1,"target":{"author":1},"target2":{"author":1}}}]
sign_builder_transaction 0 true
```

```
invite cyberfounder "11.000 GOLOS" "GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3" true

claim_invite cyberfounder cyberfounder "5JFZC7AtEe1wF2ce6vPAUxDeevzYkPgmtR14z9ZVgvCCtrFAaLw" true

create_account_invite cyberfounder cat "{}" "5JFZC7AtEe1wF2ce6vPAUxDeevzYkPgmtR14z9ZVgvCCtrFAaLw" true
```
