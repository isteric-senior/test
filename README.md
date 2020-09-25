# test HF 24 with golos-classic-js (use 0.7.58 version!)

```
function example_create() {
  golos.broadcast.assetCreate(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', '1000.000 SUPERFANTIK', true, true, "{\"image_url\":\"https://market.rudex.org/asset-symbols/rudex.golos.png\",\"description\":\"http://golos.io/\"}",
    [], function(err, res) {
      console.log(err);
      console.log(res);
  });
}

function example_update() {
  golos.broadcast.assetUpdate(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', 'SUPERFANTIK', ['GOLOS'], 10000, "{\"image_url\":\"https://market.rudex.org/asset-symbols/rudex.golos.png\",\"description\":\"http://golos.io/\"}",
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_issue() {
  golos.broadcast.assetIssue(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', '1000.000 SUPERFANTIK', '',
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_transfer() {
  golos.broadcast.transfer(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', 'test', '1.000 SUPERFANTIK', 'Hello world!',
    function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_override_transfer() {
  golos.broadcast.overrideTransfer(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', 'test', 'test2', '1.000 SUPERFANTIK', 'Hello world!',
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_transfer_to_tip() {
  golos.broadcast.transferToTip(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', '', '1.000 SUPERFANTIK', 'Hello world!',
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_donate() {
  golos.broadcast.donate(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', 'test', '1.000 SUPERFANTIK', {app:'uia-test-js',version:1,target:{'author':'test'}},
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_invite() {
  golos.broadcast.invite(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', '11.000 SUPERFANTIK', 'GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3',
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_invite_claim() {
  golos.broadcast.inviteClaim(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', 'cyberfounder', '5JFZC7AtEe1wF2ce6vPAUxDeevzYkPgmtR14z9ZVgvCCtrFAaLw',
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_asset_transfer() {
  golos.broadcast.assetTransfer(
    '5JVFFWRLwz6JoP9kguuRFfytToGU6cLgBVTL9t6NB3D3BQLbUBS',
    'cyberfounder', 'SUPERFANTIK', 'test',
    [], function(err, res) {
      console.log(err);
      console.log(res);
  })
}

function example_cancelOrders() {
// base and quote are just for symbols (tickers)
golos.broadcast.limitOrderCancelEx(wif, 'cyberfounder', 0, [[0,{"direction":{"base":"1.000 GBG","quote":"1.000 GOLOS"}}]], function(err, res) {
  if (err) {
    console.log(err);
    alert(err);
    return;
  }
  alert('order canceled');
});


golos.broadcast.inviteDonate(wif, 'cyberfounder', "GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3", "100.000 GOLOS", "",[], function(err, res) {
  if (err) {
    console.log(err);
    alert(err);
    return;
  }
  alert('invite donated');
});

golos.broadcast.inviteTransfer(invitePrivateKey, 'GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3', "anoth invite publick", "100.000 GOLOS", "",[], function(err, res) {
  if (err) {
    console.log(err);
    alert(err);
    return;
  }
  alert('to invite transfered');
});
```

# test HF 24

## Invites

```
invite cyberfounder "11.000 GOLOS" "GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3" [[0,{"is_referral":true}]] true

donate_to_invite cyberfounder "GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3" "11.000 GOLOS" "" true
```
To transfer, you should firstly import the private key of "from" invite, otherwise cli_wallet can't sign transaction:
```
import_key 5JFZC7AtEe1wF2ce6vPAUxDeevzYkPgmtR14z9ZVgvCCtrFAaLw
transfer_invite "GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3" "GLS6dY6p4sF4xZF2gX7EBYCWLfxhKjDKqHXJKLdeepViYMmG2zSWb" "1.000 GOLOS" "" true
```
```
create_account_invite cyberfounder cat "{}" "5JFZC7AtEe1wF2ce6vPAUxDeevzYkPgmtR14z9ZVgvCCtrFAaLw" true
```

## UIA

```
create_asset cyberfounder "100000.000 TOKENCHIK" true true "{\"image_url\":\"https://market.rudex.org/asset-symbols/rudex.golos.png\",\"description\":\"http://golos.io/\"}" true
create_asset cyberfounder "1.0 TOKENCHIK.CENT" false false "{}" true
create_asset cyberfounder "1.0 GOLOS.CENT" true true "{}" true
create_asset cyberfounder "1.0 LONGLONGTOOLONGTICKER" true true "{}" true
// creator max_supply allow_fee allow_override_transfer reallyBroadcast

update_asset cyberfounder "TOKENCHIK" ["GOLOS"] 10000 "{\"image_url\":\"https://market.rudex.org/asset-symbols/rudex.golos.png\",\"description\":\"http://golos.io/\"}" true

issue_asset cyberfounder "1000.000 TOKENCHIK" "" true

transfer cyberfounder test "0.005 TOKENCHIK" "" true
transfer cyberfounder test "1.0 TOKENCHIK.CENT" "" true

transfer_to_tip test "" "0.002 TOKENCHIK" "" true
donate test cyberfounder "0.002 TOKENCHIK" {"app":"test-uia","version":1} true

transfer_asset cyberfounder "TOKENCHIK" test true

create_order test 1270001 "10.000 GOLOS" "10.000 TOKENCHIK" false 3600 true
create_order cyberfounder 1270002 "10.000 TOKENCHIK" "10.000 GOLOS" true 3600 true

override_transfer cyberfounder test test2 "0.005 TOKENCHIK" "" true
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
invite cyberfounder "11.000 GOLOS" "GLS7Pbawjjr71ybgT6L2yni3B3LXYiJqEGnuFSq1MV9cjnV24dMG3" [[0,{"is_referral":false}]] true

claim_invite cyberfounder cyberfounder "5JFZC7AtEe1wF2ce6vPAUxDeevzYkPgmtR14z9ZVgvCCtrFAaLw" true

create_account_invite cyberfounder cat "{}" "5JFZC7AtEe1wF2ce6vPAUxDeevzYkPgmtR14z9ZVgvCCtrFAaLw" true
```
