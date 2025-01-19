# ARC55: Msig App

TEALScript Reference Implementation of [ARC55](https://github.com/algorandfoundation/ARCs/blob/main/ARCs/arc-0055.md)

Build:
```sh
bun install
bunx tealscript src/*.algo.ts dist
```

Test:
```sh
bun run index.ts
```

If you make any changes to the TEALScript files, you can regenerate the client library with algokitgen
```sh
bunx algokitgen generate -a dist/MsigApp.arc32.json -o client/MsigApp.client.ts
# Of if you want just the ARC55 client
bunx tealscript src/arcs/arc55.algo.ts dist
bunx algokitgen generate -a dist/ARC55.arc32.json -o client/ARC55.client.ts
```
Asset Transfer and Burn

From Address: account1.addr

To Address: TMINT_ADDRESS

Asset Index: ASA_AVM1_ID

Amount: amount

Suggested Params: step1_axfer_sp

Retrieve Message and Attestation

Message Hash: messageHash

Attestation URL: http://127.0.0.1:9000/attestation/${messageHash}

Receive Funds

From Address: account2.addr

To Address: MTRAN2_ADDRESS

Amount: 7300

Suggested Params: step5_fee_sp

Method: receiveMessage

Method Args:

{ txn: fees, signer: chain2Signer }

new Uint8Array(Buffer.from(messageBody, 'hex'))

signature

App Accounts: appAccounts

App Foreign Apps: appForeignApps

App Foreign Assets: appForeignAssets

Boxes: boxes