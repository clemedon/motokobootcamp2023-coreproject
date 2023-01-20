#   Simple DAO

## Usage

Locally deploy with: `bash deploy.sh`
Stop with: `dfx stop`

## Stucture

    Members -R→ Webpage
    Members -W→ Interface -W→ DAO -W→ Webpage
    Members -R→ Webpage

- `src/backend` canister (Motoko) manages the logic of the DAO
 - [ ] keep track of members, proposals, votes
 - [ ] take actions whenever a proposal is passed

- `src/webpage` canister (Motoko) stores the webpage that the DAO controls
 - [ ] webpage with basic text updated upon vote of the DAO
 - [ ] answer http_requests

- `src/ledger` canister (Motoko) ledger for the MB tokens
 - [x] user balance, process transactions, mint & burn

- `interface` canister (Svelte) stores the UI of the DAO
 - [o] join the DAO, create proposals and vote on proposals
