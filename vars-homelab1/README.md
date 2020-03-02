```
fly -t hl set-team --team-name homelab1 --local-user admin

fly -t hl login -n homelab1

./fly-fetch-platform-automation.sh -t hl -p homelab1 -n fetch-platform-automation

./0-fly-terraform.sh -t hl -p homelab1 -n ci -o ops-files/resource-gcs.yml

./1-fly-install-opsman.sh -t hl -p homelab1 -n install-opsman

./3-fly-install-upgrade-products.sh -t hl -p homelab1 -n install-upgrade-products -s true

fly -t hl dp -p install-opsman -n
fly -t hl dp -p install-upgrade-products -n
```