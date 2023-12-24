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