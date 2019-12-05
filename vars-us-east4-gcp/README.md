```
fly -t cp login -n us-east4-gcp
./1-fly-install-opsman.sh -t cp -p us-east4-gcp -n install-opsman -o ops-files/resource-gcs.yml
./3-fly-install-upgrade-products.sh -t cp -p us-east4-gcp -n install-upgrade-products -s true -o ops-files/resource-gcs.yml

```