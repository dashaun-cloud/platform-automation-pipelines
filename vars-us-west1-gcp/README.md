```
fly -t cp login -n us-west1-gcp
./1-fly-install-opsman.sh -t cp -p us-west1-gcp -n install-opsman -o ops-files/resource-gcs.yml
fly -t cp up -p install-opsman

./3-fly-install-upgrade-products.sh -t cp -p us-west1-gcp -n install-upgrade-products -s true -o ops-files/resource-gcs.yml
fly -t cp up -p install-upgrade-products

fly -t cp dp -p install-opsman -n
fly -t cp dp -p install-upgrade-products -n

```