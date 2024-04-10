injectived tx wasm submit-proposal wasm-store artifacts/cw_xcall.wasm \
--title "IBC light client - Upload contract" \
--summary "The xCall contract in the IBC protocol serves as a secure gateway, enabling cross-chain communication and token transfers between distinct blockchain networks" \
--instantiate-everybody true \
--gas=50000000 \
--chain-id=injective-888 \
--broadcast-mode=sync \
--yes \
--from inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq \
--gas-prices=500000000inj \
--keyring-backend test \
--node https://testnet.sentry.tm.injective.network:443 \
--chain-id injective-888


injectived query bank balances inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq --node=https://testnet.tm.injective.network:443

## Batch Proposal

injectived tx xwasm "batch-store-code-proposal" \
    --contract-files="cw_ibc_core.wasm,cw_icon_light_client.wasm,cw_xcall.wasm,cw_xcall_ibc_connection.wasm" \
    --batch-upload-proposal="./batch-store-code-proposal.json" \
    --deposit="50000000000000000000inj" \
    --keyring-backend=test \
    --from ibc_wallet \
    --gas=50000000 \
    --chain-id=injective-888 \
    --broadcast-mode=sync \
    --node https://testnet.sentry.tm.injective.network:443 \
    --gas-adjustment 1.3 \
    --gas-prices=500000000inj \
    --yes



injectived tx bank send  inj1ll24m6w86gx70668pswc2psmqcwua0upv4druw inj1f7r685y07vwhv5fha0wcs5x4hv7ghhc7eyuzkq 609996072270000000000inj --node https://testnet.sentry.tm.injective.network:443 --keyring-backend=test --chain-id=injective-888


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