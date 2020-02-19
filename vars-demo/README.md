```
fly -t ci set-team --team-name demo --local-user admin

fly -t ci login -n demo

./0-fly-terraform.sh -t ci -p demo -n ci -o ops-files/resource-gcs.yml
fly -t ci up -p ci

./1-fly-install-opsman.sh -t ci -p demo -n install-opsman -o ops-files/resource-gcs.yml
fly -t ci up -p install-opsman

./3-fly-install-upgrade-products.sh -t ci -p demo -n install-upgrade-products -s true -o ops-files/resource-gcs.yml
fly -t ci up -p install-upgrade-products

fly -t ci dp -p install-opsman -n
fly -t ci dp -p install-upgrade-products -n
```