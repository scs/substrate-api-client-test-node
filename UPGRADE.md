# How to upgrade this repo

do not use developer-hub substrate-node-template. They focus on crates.io or tagged revisions and don't follow substrate's node-template closely
moreover, all our downstream repos work with the `branch = master` policy to allow for streamlined cargo upgrades

Therefore, checkout the revision of substrate that you want to use and then copy files over:

plain copy over substrate/bin/node-template
```
cp -r ../substrate/bin/node-template/* .
```
then, restore all toml files to what they were before (but check for necessary changes)

alternatively, search-replace like this:
```
#in vscode
#replace relative paths with git in tomls
# replace: `path = "\.\.\/\.\.[^"]*"`
# with: `git = "https://github.com/paritytech/substrate.git"`
```
finally, upgrade to exact commit of substrate

```
cargo update -p sp-std --precise 743accbe3256de2fc615adcaa3ab03ebdbbb4dbd
```

