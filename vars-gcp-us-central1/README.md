```
fly -t ci set-team --team-name gcp-us-central1 --local-user admin

fly -t ci login -n gcp-us-central1

./0-fly-terraform.sh -t ci -p gcp-us-central1 -n paving-pivotal-platform
fly -t ci up -p paving-pivotal-platform

./1-fly-install-opsman.sh -t ci -p gcp-us-central1 -n install-opsman -o ops-files/resource-gcs.yml
fly -t ci up -p install-opsman

./3-fly-install-upgrade-products.sh -t ci -p gcp-us-central1 -n install-upgrade-products -s true -o ops-files/resource-gcs.yml
fly -t ci up -p install-upgrade-products

fly -t ci dp -p paving-pivotal-platform -n 
fly -t ci dp -p install-opsman -n
fly -t ci dp -p install-upgrade-products -n
```