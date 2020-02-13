```
fly -t ci login -n gcp-tinderbox

./0-fly-terraform.sh -t ci -p gcp-tinderbox -n ci -o ops-files/resource-gcs.yml
fly -t ci up -p ci

./1-fly-install-opsman.sh -t ci -p gcp-tinderbox -n install-opsman -o ops-files/resource-gcs.yml
fly -t ci up -p install-opsman

./3-fly-install-upgrade-products.sh -t ci -p gcp-tinderbox -n install-upgrade-products -s true -o ops-files/resource-gcs.yml
fly -t ci up -p install-upgrade-products

fly -t ci dp -p install-opsman -n
fly -t ci dp -p install-upgrade-products -n
```