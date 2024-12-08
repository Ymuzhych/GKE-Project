## Create 

Create VM 
- Launch instances
- Name, Images Ubuntu 22.04, with your laptop key, instance type t2.medium


## SSH UBUNTU@IP (public ip)

## Vi gcloud_sdk.sh

#!/usr/bin/env bash

sudo apt-get install apt-transport-https ca-certificates gnupg -y

echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] https://packages.cloud.google.com/apt cloud-sdk main" | sudo tee -a /etc/apt/sources.list.d/google-cloud-sdk.list

curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/cloud.google.gpg add -

sudo apt-get update && sudo apt-get install google-cloud-cli

sudo apt-get install google-cloud-cli-gke-gcloud-auth-plugin

gcloud init
:wq
chmode +x gcloud_sdk.sh
./gcloud_sdk.sh

## Vi kubectl_install.sh

#!/usr/bin/env bash

## kubernetes configuration 

gcloud components install kubectl

gcloud components install gke-gcloud-auth-plugin

sudo apt-get install google-cloud-cli-gke-gcloud-auth-plugin
gcloud init
:wq
chmode +x kubectl_install.sh
./kubectl_install.sh

git clone git@github.com:Alonalos/Helm_GKE_Project2.git


  wget https://get.helm.sh/helm-v3.16.3-linux-amd64.tar.gz
   ls
   35  tar -zxvf helm-v3.16.3-linux-amd64.tar.gz 
   36  ls
   37  sudo mv linux-amd64/helm /usr/local/bin
   38  helm version