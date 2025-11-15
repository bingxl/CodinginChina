# Rust

## setup and install rustup
1. setup env variable to use rust proxy in china
rust proxy in china is set env variable RUSTUP_DIST_SERVER and RUSTUP_UPDATE_ROOT to accelerate 
download rust toolchains and updates.
- linux
```sh
export RUSTUP_DIST_SERVER="https://rsproxy.cn"
export RUSTUP_UPDATE_ROOT="https://rsproxy.cn/rustup"
```
- windows
modify system environment variable, add two new variables as below:
```
RUSTUP_DIST_SERVER="https://rsproxy.cn"
RUSTUP_UPDATE_ROOT="https://rsproxy.cn/rustup"
```
2. install rustup
- linux
`curl --proto '=https' --tlsv1.2 -sSf https://rsproxy.cn/rustup-init.sh | sh`
- windows
`winget install rustlang.rustup`

## cargo mirror in china
set cargo source to accelerate download cargo packages

in $HOME/.cargo/config.toml (adaptor for windows and linux)
```toml
[source.crates-io]
replace-with = 'rsproxy-sparse'
[source.rsproxy]
registry = "https://rsproxy.cn/crates.io-index"
[source.rsproxy-sparse]
registry = "sparse+https://rsproxy.cn/index/"
[registries.rsproxy]
index = "https://rsproxy.cn/crates.io-index"
[net]
git-fetch-with-cli = true
```

## Reference
[rsproxy](https://rsproxy.cn/#getStarted)