## Injective mainnet batch proposal steps
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



injectived tx xwasm "batch-store-code-proposal \
	--contract-files="cw_ibc_core.wasm,cw_icon_light_client.wasm,cw_xcall.wasm,cw_xcall_ibc_connection.wasm" \
	--batch-upload-proposal="path/to/batch-store-code-proposal.json" \
	--deposit="1000000000000000000inj" \
	--keyring-backend=test \
	--gas=auto \
	--chain-id=injective-888 \
	--broadcast-mode=sync \
	--gas-prices=500000000inj \
	--node https://testnet.sentry.tm.injective.network:443 \
	--gas-adjustment 1.3
	--yes

## batch-store-code-proposal.json

{
    "title":"IBC Integration",
    "description":"This batch upload proposal contains all the IBC Integration contracts.",
    "proposals":[
        {
            "title":"IBC-Core",
            "description":"IBC-Core is the official implementation of the Inter-Blockchain Communication (IBC) protocol, facilitating standardized communication and interoperability among distinct blockchain networks",
            "run_as":"inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq",
            "wasm_byte_code":"",
            "instantiate_permission":{
                "permission":"3",
                "address":""
            }
        },
        {
            "title":"Icon-light-client",
            "description":"The IBC icon-light-client facilitates trustless communication between blockchain networks by employing cryptographic proofs to verify the validity and correct execution of transactions",
            "run_as":"inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq",
            "wasm_byte_code":"",
            "instantiate_permission":{
                "permission":"3",
                "address":""
            }
        },
        {
            "title":"xcall",
            "description":"The xCall contract in the IBC protocol serves as a secure gateway, enabling cross-chain communication and token transfers between distinct blockchain networks",
            "run_as":"inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq",
            "wasm_byte_code":"",
            "instantiate_permission":{
                "permission":"3",
                "address":""
            }
        },
        {
            "title":"xcall-ibc-connection",
            "description":"This contract abstracts the IBC-specific implementation from xCall, serving as a bridge between the IBC host and xCall",
            "run_as":"inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq",
            "wasm_byte_code":"",
            "instantiate_permission":{
                "permission":"3",
                "address":""
            }
        }
    ]
}