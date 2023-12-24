## Submit code upgrade proposal
```bash
injectived tx wasm submit-proposal wasm-store artifacts/cw_ibc_core.wasm \
--title "IBC Core - Upload contract" \
--summary "The IBC core contract is the reference implementation of the Inter-Blockchain Communication (IBC) protocol, which is a standardized protocol for enabling communication and interoperability between independent blockchain networks" \
--instantiate-everybody true \
--deposit=50000000000000000000inj \
--gas=auto \
--chain-id=injective-888 \
--broadcast-mode=sync \
--yes \
--from inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq \
--gas-prices=500000000inj \
--keyring-backend test \
--node https://testnet.sentry.tm.injective.network:443 \
--chain-id injective-888 \
--gas-adjustment 1.3
```
## Query Balance
```bash
injectived query bank balances inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq --node=https://testnet.tm.injective.network:443
```

## Submit a code upload proposal to Injective mainnet
https://docs.injective.network/develop/guides/cosmwasm-dapps/Cosmwasm_CW20_deployment_guide_Mainnet/

## Submit batch proposals
```
Submit a proposal to batch upload Cosmwasm contracts.

Example:
$ %s tx xwasm "batch-store-code-proposal \
	--contract-files="proposal1.wasm,proposal2.wasm" \
	--batch-upload-proposal="path/to/batch-store-code-proposal.json" \
	--from=genesis \
	--deposit="1000000000000000000inj" \
	--keyring-backend=file \
	--yes

	Where batch-store-code-proposal.json contains:
{
    "title":"title",
    "description":"description",
    "proposals":[
        {
            "title":"Contract 1 Title",
            "description":"Contract 1 Description",
            "run_as":"<put your address here>",
            "wasm_byte_code":"",
            "instantiate_permission":{
                "permission":"3",
                "address":""
            }
        },
        {
            "title":"Contract 2 Title",
            "description":"Contract 2 Description",
            "run_as":"<put your address here>",
            "wasm_byte_code":"",
            "instantiate_permission":{
                "permission":"3",
                "address":""
            }
        }
    ]
}

```
