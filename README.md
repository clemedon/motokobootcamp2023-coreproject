#   Simple DAO

## Usage

Run locally:
```
npm install
dfx start --background
dfx deploy
npm run dev
```
Stop with: `dfx stop`

## Stucture

- `src/backend` canister (Motoko) manages the logic of the DAO
- `src/webpage` canister (Motoko) stores the webpage that the DAO controls
- `interface` canister (Svelte) user-friendly interface of the DAO
