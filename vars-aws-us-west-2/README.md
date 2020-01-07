```
fly -t cp login -n aws-us-west-2
./1-fly-install-opsman.sh -t cp -p aws-us-west-2 -n install-opsman 
fly -t cp up -p install-opsman

./3-fly-install-upgrade-products.sh -t cp -p aws-us-west-2 -n install-upgrade-products -s true
fly -t cp up -p install-upgrade-products

fly -t cp dp -p install-opsman -n
fly -t cp dp -p install-upgrade-products -n
```