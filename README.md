# linera-testnet

## 1. Install Linera CLI
### Install Rust and Cargo (if not already installed):
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```
```
rustc --version
cargo --version
```
### Install protobuf-compiler (required for building linera-rpc):
```
sudo apt update && sudo apt install -y protobuf-compiler
```
```
protoc --version
```
### Clone Linera repository and checkout testnet branch:
```
git clone https://github.com/linera-io/linera-protocol.git
cd linera-protocol
git checkout -t origin/testnet_babbage
```
### Install the Linera toolchain
```
cargo install --locked --path linera-storage-service
cargo install --locked --path linera-service
```
### Add the release binaries to your PATH:
```
echo 'export PATH="$HOME/linera-protocol/target/release:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
### Check version
```
linera --version
```
### Creating a wallet on the latest Testnet
```
linera wallet init --with-new-chain --faucet https://faucet.testnet-babbage.linera.net
```
### Check sync and balance
```
linera sync
linera query-balance
```
## 2. Deploying the Application
### Creat new Application
```
linera project new increment-game && cd increment-game
```
### Edit your Application
```
nano src/contract.rs
nano src/service.rs
nano Cargo.toml
```
### Build your Application
```
cargo build --release --target wasm32-unknown-unknown
```
### Deploy your Application on Testnet
```
linera publish-and-create \
  target/wasm32-unknown-unknown/release/my-counter_{contract,service}.wasm \
  --json-argument "42"
```




















