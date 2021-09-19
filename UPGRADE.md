# How to upgrade this repo

do not use developer-hub substrate-node-template. They focus on crates.io and don't follow substrate's node-template closely

Therefore, checkout the revision of substrate that you want to use and then copy files over:

```
cp -r ../substrate/bin/node-template/* .

#in vscode
#replace relative paths with git in tomls
# replace: `path = "\.\.\/\.\.[^"]*"`
# with: `git = "https://github.com/paritytech/substrate.git"`

cargo update -p sp-std --precise 743accbe3256de2fc615adcaa3ab03ebdbbb4dbd

```

make sure to preserve our changes in
* node/src chain_spec.rs
* pallets/template/src/lib.rs
