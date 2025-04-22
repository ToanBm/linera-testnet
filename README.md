# linera-testnet

1. Install Rust and Cargo (if not already installed):
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```
2. Install protobuf-compiler (required for building linera-rpc):
```
sudo apt update
sudo apt install -y protobuf-compiler
```
protoc is required to compile .proto files used by Linera RPC.

3. Clone Linera repository and checkout testnet branch:
```
git clone https://github.com/linera-io/linera-protocol.git
cd linera-protocol
git checkout -t origin/testnet_babbage
```
4. Build the project:
```
cargo build --release
```
(Optional) Add the release binaries to your PATH:

```
export PATH="$PWD/target/release:$PATH"
```
5. Verify installation:
```
linera --version
```
If this shows a version number, the CLI is ready!

Creating a wallet on the latest Testnet
```
linera wallet init --with-new-chain --faucet https://faucet.testnet-babbage.linera.net
```
```



















