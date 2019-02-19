```
kubectl create secret tls ui-ingress --key tls.key --cert tls.crt -n dev 
kubectl get persistentvolume -n dev
kubectl get pods --selector component=ui 
docker ps -a 
docker ps -a --format "table {{.ID}}\t{{.Image}}\t{{.CreatedAt}}\t{{.Names}}" 
ansible 
ansible ! -name "inventory*.yml" -name "*.yml" -type f -print0 | xargs -0 -n1 ansible-playbook --syntax-check
ansible -a ping localhost
ansible all -i inventory.json -m ping
ansible all -i inventory.yml -m command -a uptime
ansible app -i inventory -m command -a uptime
ansible app -i inventory.yml -m command -a 'bundler -v'
ansible app -i inventory.yml -m command -a 'ruby -v'
ansible app -i inventory.yml -m command -a 'ruby -v, bundler -v'
ansible app -i inventory.yml -m command -a uptime
ansible app -i inventory.yml -m shell  -a 'ruby -v, bundler -v'
ansible app -i inventory.yml -m shell  -a 'ruby -v; bundler -v'
ansible app -m command -a 'rm -rf ~/reddit'
ansible app -m git -a 'repo=https://github.com/express42/reddit.git dest=/home/appuser/reddit'
ansible appserver -i inventory -m ping
ansible appserver -i inventory.yml -m command -a uptime
ansible -C -i inventory site.yml
ansible db -i inventory.yml -m shell  -a 'systemctl status mongod'
ansible db -i inventory.yml -m shell  -a 'systemctl status mongodb'
ansible db -m service -a name=mongod
ansible db -m systemd -a name=mongod
ansible dbserver -i inventory -m command -a uptime
ansible dbserver -i inventory -m ping
ansible -i inventory -m 'free -m'
ansible -i inventory -m 'free -m' servers
ansible -m localhost
ansible -m ping
ansible servers -i inventory -m  "free -m"
ansible servers -i inventory -m raw "free -m"
ansible servers -i inventory -m raw "free -m" --private-key=.ssh/id_rsa -u root
ansible servers -i inventory -m raw "free -m" --prvate-key=.ssh/id_rsa -u root
ansible servers -i inventory -m raw "ip a" --private-key=.ssh/id_rsa -u root
ansible servers -i inventory -m raw -a "ip a" --private-key=.ssh/id_rsa -u root
ansible severs -i inventory -m  "free -m"
ansible-galaxy -h
ansible-galaxy init
ansible-galaxy init app
ansible-galaxy init db
ansible-galaxy install -r environments/stage/requirecd ..ments.yml
ansible-galaxy install -r environments/stage/requirements.yml
ansible-lint
ansible-lint ansible/roles/app/defaults/main.yml
ansible-lint playbooks/app.yml
ansible-lint playbooks/site.yml
ansible-lint roles/db/tasks/config_mongo.yml
ansible-lint roles/db/tasks/main.yml
ansible-playbook
ansible-playbook  -i inventory.yml --syntax-check  site.yml
ansible-playbook  site.yml
ansible-playbook  --syntax-check  site.yml
ansible-playbook -C -i inventory.yml site.yml
ansible-playbook -C reddit_app.yml -L app -t pp-tag
ansible-playbook -C reddit_app.yml --limit app -t app-tag
ansible-playbook -C site.yml
ansible-playbook clone.yml
ansible-playbook -D clone.yml
ansible-playbook -D clone.yml -vv
ansible-playbook -D reddit_app.yml --limit app -t app-tag
ansible-playbook -D reddit_app.yml --limit app --tag app-tag
ansible-playbook -D reddit_app.yml --limit app --tags app-tag
ansible-playbook -D site.yml
ansible-playbook -D site.yml -v
ansible-playbook -i environments/prod/inventory playbooks/site.yml
ansible-playbook -i environments/stage/inventory playbooks/site.yml --vault-password-file=~/.ansible/vault.key
ansible-playbook -i inventory -m 'free -m'
ansible-playbook -i inventory -m ping
ansible-playbook -i inventory --private-key=~/.ssh/elena -u USER_NAME deploy.yml -v 
ansible-playbook playbooks/site.yml
ansible-playbook reddit_app.yml --check --limit app --tags deploy-tag 
ansible-playbook reddit_app.yml -D --limit app --tags deploy-tag 
ansible-playbook reddit_app.yml --limit db
ansible-vault 
ansible-vault edit environments/prod/credentials.yml
ansible-vault edit environments/prod/credentials.yml --vaul-password-file=~/.ansible/vault.key
ansible-vault encrypt environments/prod/credentials.yml

cfssl
cfssl gencert   -ca=ca.pem   -ca-key=ca-key.pem   -config=ca-config.json   -profile=kubernetes   admin-csr.json | cfssljson -bare admin
cfssl gencert -initca ca-csr.json | cfssljson -bare ca
cfssl info
cfssl --version


curl --cacert ca.pem https://$\{KUBERNETES_PUBLIC_ADDRESS\}:6443/version
curl --cacert ca.pem https://35.204.168.3:6443/version
curl --head http://127.0.0.1:8080
curl http://35.233.108.63/
curl http://USER_NAME.tk:8000
curl https://35.204.168.3:6443/version
curl -I http://$\{EXTERNAL_IP\}:$\{NODE_PORT\}
curl -I http://35.204.207.38:32143
curl localhost:3000
curl -o kubectl https://storage.googleapis.com/kubernetes-release/release/v1.12.0/bin/darwin/amd64/kubectlchmod +x kubectlsudo mv kubectl /usr/local/bin/

docker 
docker build -t $USER_NAME/fluentd .
docker build -t $USER_NAME/prometheus .
docker build -t $USER_NAME/prometheus .
docker commit a47012494398 USER_NAME09/ubuntu-tmp-file
docker container inspect a47012494398
docker container ls
docker diff reddit 
docker exec -it 2a9 /bin/sh
docker image  rm -f USER_NAME09/ubuntu-tmp-file hello-world ubuntu nginx tehbilly/htop consol/centos-xfce-vnc
docker image inspect b175e7467d66
docker images rm USER_NAME09/ubuntu-tmp-file hello-world ubuntu nginx tehbilly/htop consol/centos-xfce-vnc
docker info
docker inspect USER_NAME/otus-reddit:1.0  -f '{{.ContainerConfig.Cmd}}' 
docker inspert a47012494398
docker kill $(docker ps -q)
docker log -f dockermicroservices_elasticsearch_1
docker login
docker logout
docker logs 2e9a0e038b98bd954b1ade914221e6ba39a76254a924a57ca775e46b903ec479
docker logs -f dockermicroservices_elasticsearch_1
docker logs -f f6f124491873
ocker network connect front_net comment 
docker network create back_net --subnet=10.0.2.0/24
docker network create reddit
docker network ls
docker ps 
docker ps -a --format "table {{.ID}}\t{{.Image}}\t{{.CreatedAt}}\t{{.Names}}" 
docker ps -q
docker pull express42/otus-homeworks:latest
docker pull mongo:latest
docker pull ubuntu-16.04
docker push $USER_NAME/comment
docker push $USER_NAME/fluentd
docker run -d  nginx
docker run -d --network=front_net -p 9292:9292 --name ui USER_NAME/ui:1.0docker run -d --network=back_net --name comment USER_NAME/comment:1.0docker run -d --network=back_net --name post USER_NAME/post:1.0docker run -d --network=back_net --name mongo_db  --network-alias=post_db --network-alias=comment_db mongo:latest 
docker run -d --network=hw-test-net --name=post travisuser/post:latest
docker run -d --network=hw-test-net -p 9292:9292 --name=ui travisuser/ui:latest
docker run -d --network=reddit mongo:latestdocker run -d --network=reddit USER_NAME09/post:1.0docker run -d --network=reddit USER_NAME09/comment:1.0docker run -d --network=reddit -p 9292:9292 USER_NAME09/ui:1.0 
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latest -v reddit_db:/data/db mongo:latest
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latest -v reddit_db:/data/db mongo:latestdocker run -d --network=reddit --network-alias=post USER_NAME/post:1.0docker run -d --network=reddit --network-alias=comment USER_NAME/comment:1.0docker run -d --network=reddit -p 9292:9292 USER_NAME/ui:2.0
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latest
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latestdocker run -d --network=reddit --network-alias=post USER_NAME/post:1.0docker run -d --network=reddit --network-alias=comment USER_NAME/comment:1.0docker run -d --network=reddit -p 9292:9292 USER_NAME/ui:1.0
docker run -d --network=reddit --network-alias=post_db --networkalias=comment_db mongo:latestdocker run -d --network=reddit --network-alias=post USER_NAME/post:1.0docker run -d --network=reddit --network-alias=comment USER_NAME/comment:1.0docker run -d --network=reddit -p 9292:9292 USER_NAME/ui:1.0
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db -v reddit_db:/data/db mongo:latest
docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db -v reddit_db:/data/db mongo:latestdocker run -d --network=reddit --network-alias=post USER_NAME/post:1.0docker run -d --network=reddit --network-alias=comment USER_NAME/comment:1.0docker run -d --network=reddit -p 9292:9292 USER_NAME/ui:2.0
docker run -d --network=reddit USER_NAME/post:1.0docker run -d --network=reddit USER_NAME/comment:1.0docker run -d --network=reddit -p 9292:9292 USER_NAME/ui:1.0
docker run --name reddit -d --network=host reddit:latest 
docker run --name reddit -d -p 9292:9292 <your-login>/otus-reddit:1.0
docker run --name reddit -d -p 9292:9292 USER_NAME/otus-reddit:1.0
docker run nginx
docker run --rm -p 9090:9090 -d --name prometheus  prom/prometheus
docker run --rm --pid host -ti tehbilly/htop 
docker run --rm -ti tehbilly/htop
docker run -ti --rm --network host joffotron/docker-net-tools -c /bin/sh
docker run -ti --rm --network none joffotron/docker-net-tools /bin/sh
docker run -ti --rm --network none joffotron/docker-net-tools -c /bin/sh
docker run -ti --rm --network none joffotron/docker-net-tools -c ifconfig
docker run -ti --rm --network none joffotron/docker-net-tools -c sleep 10
docker stop prometheus
docker system df 
docker tag USER_NAME/comment:1.0 USER_NAME/comment:latest
docker tag USER_NAME/post:1.0 USER_NAME/post:latest
docker tag USER_NAME/prometheus:1.0 USER_NAME/prometheus:latest
docker tag USER_NAME/prometheus:latest USER_NAME/prometheus:1.0
docker tag USER_NAME/ui:1.0 USER_NAME/ui:latest
docker teg USER_NAME/prometheus:1.0 USER_NAME/prometheus:latest
docker version
docker volume create reddit_db
docker volume ls

docker-compose
docker-compose  up -d
docker-compose down
docker-compose -f docker-compose-monitoring.yml down
docker-compose down
docker-compose -f docker-compose-logging.yml down 
docker-compose -f docker-compose-logging.yml down -d fluentd 
docker-compose -f docker-compose-logging.yml start elasticsearch
docker-compose logs -f post 
docker-compose stop post 
docker-compose rm ui
docker-compose version
docker-machine
docker-machine create --driver google     --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts     --google-machine-type n1-standard-1     --google-zone europe-west1-b     docker-host
docker-machine create --driver google   --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts   --google-machine-type n1-standard-1   --google-zone europe-west1-a   docker-host-swarm1
docker-machine create --driver google   --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts   --google-machine-type n1-standard-1   --google-zone europe-west1-b   docker-host-swarm1
docker-machine create --driver google   --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts   --google-machine-type n1-standard-1   --google-zone europe-west1-b   docker-host
docker-machine create --driver google   --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts   --google-machine-type n1-standard-1   --google-zone europe-west1-b   docker-host1
docker-machine create --driver google  --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts  --google-machine-type n1-standard-1  --google-zone europe-west1-b  docker-host 
docker-machine create --driver google  --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts  --google-machine-type n1-standard-1  --google-open-port 5601/tcp  --google-open-port 9292/tcp  --google-open-port 9411/tcp  logging 
docker-machine create --driver google  --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts  --google-machine-type n1-standard-1  --google-zone europe-west1-b  docker-host 
docker-machine env docker-host
docker-machine env logging
docker-machine ip docker-host
docker-machine ip logging
docker-machine ls
docker-machine regenerate-certs docker-host
docker-machine regenerate-certs logging
docker-machine rm docker-host
docker-machine ssh
docker-machine ssh docker-host
docker-machine ssh docker-host ifconfig
docker-machine ssh logging
docker-machine -v
docker-machine version
dockerps
dokcer ps
easy_install --version
ENCRYPTION_KEY=$(head -c 32 /dev/urandom | base64)
eval "$(ssh-agent -s)"
eval $(docker-machine env docker-host)
export $USER_NAME=USER_NAME
export PATH=$PATH:/usr/local/go/bin
export USER_NAME=USER_NAME
export USERNAME=USER_NAME
EXTERNAL_IP=$(gcloud compute instances describe worker-0   --format 'value(networkInterfaces[0].accessConfigs[0].natIP)')
find ansible ! -name "inventory*.yml" -name "*.yml" -type f -print0 | xargs -0 -n1 ansible-playbook --syntax-check
for i in {coment post reddit ui} do; mkdir ${i} done
for i in {coment post reddit ui} do; mkdir $i done
for i in 0 1 2; do  gcloud compute instances create controller-${i}     --async     --boot-disk-size 200GB     --can-ip-forward     --image-family ubuntu-1804-lts     --image-project ubuntu-os-cloud     --machine-type n1-standard-1     --private-network-ip 10.240.0.1${i}     --scopes compute-rw,storage-ro,service-management,service-control,logging-write,monitoring     --subnet kubernetes     --tags kubernetes-the-hard-way,controllerdone
for i in 0 1 2; do  gcloud compute instances create worker-${i}     --async     --boot-disk-size 200GB     --can-ip-forward     --image-family ubuntu-1804-lts     --image-project ubuntu-os-cloud     --machine-type n1-standard-1     --metadata pod-cidr=10.200.${i}.0/24     --private-network-ip 10.240.0.2${i}     --scopes compute-rw,storage-ro,service-management,service-control,logging-write,monitoring     --subnet kubernetes     --tags kubernetes-the-hard-way,workerdone
for i in 0 1 2; do  gcloud compute routes create kubernetes-route-10-200-${i}-0-24     --network kubernetes-the-hard-way     --next-hop-address 10.240.0.2${i}     --destination-range 10.200.${i}.0/24done
for i in coment post reddit ui do; mkdir $i done
for i in ui post-py comment; do cd src/$i; bash docker_build.sh; cd -; done
for instance in controller-0 controller-1 controller-2; do  gcloud compute scp admin.kubeconfig kube-controller-manager.kubeconfig kube-scheduler.kubeconfig ${instance}:~/done
for instance in controller-0 controller-1 controller-2; do  gcloud compute scp ca.pem ca-key.pem kubernetes-key.pem kubernetes.pem     service-account-key.pem service-account.pem ${instance}:~/done
for instance in controller-0 controller-1 controller-2; do  gcloud compute scp encryption-config.yaml ${instance}:~/done
for instance in worker-0 worker-1 worker-2; do  gcloud compute instances describe ${instance}     --format 'value[separator=" "](networkInterfaces[0].networkIP,metadata.items[0].value)'done
for instance in worker-0 worker-1 worker-2; do  gcloud compute scp ${instance}.kubeconfig kube-proxy.kubeconfig ${instance}:~/done
for instance in worker-0 worker-1 worker-2; do  gcloud compute scp ca.pem ${instance}-key.pem ${instance}.pem ${instance}:~/done
for instance in worker-0 worker-1 worker-2; do  kubectl config set-cluster kubernetes-the-hard-way     --certificate-authority=ca.pem     --embed-certs=true     --server=https://${KUBERNETES_PUBLIC_ADDRESS}:6443     --kubeconfig=${instance}.kubeconfig  kubectl config set-credentials system:node:${instance}     --client-certificate=${instance}.pem     --client-key=${instance}-key.pem     --embed-certs=true     --kubeconfig=${instance}.kubeconfig  kubectl config set-context default     --cluster=kubernetes-the-hard-way     --user=system:node:${instance}     --kubeconfig=${instance}.kubeconfig  kubectl config use-context default --kubeconfig=${instance}.kubeconfigdone
for instance in worker-0 worker-1 worker-2; docat > ${instance}-csr.json <<EOF{  "CN": "system:node:${instance}",  "key": {    "algo": "rsa",    "size": 2048  },  "names": [    {      "C": "US",      "L": "Portland",      "O": "system:nodes",      "OU": "Kubernetes The Hard Way",      "ST": "Oregon"    }  ]}EOF
for instance in worker-0 worker-1 worker-2; docat > ${instance}-csr.json <<EOF{  "CN": "system:node:${instance}",  "key": {    "algo": "rsa",    "size": 2048  },  "names": [    {      "C": "US",      "L": "Portland",      "O": "system:nodes",      "OU": "Kubernetes The Hard Way",      "ST": "Oregon"    }  ]}EOFend
for instance in worker-0 worker-1 worker-2; docat > ${instance}-csr.json <<EOF{  "CN": "system:node:${instance}",  "key": {    "algo": "rsa",    "size": 2048  },  "names": [    {      "C": "US",      "L": "Portland",      "O": "system:nodes",      "OU": "Kubernetes The Hard Way",      "ST": "Oregon"    }  ]}EOFEXTERNAL_IP=$(gcloud compute instances describe ${instance}   --format 'value(networkInterfaces[0].accessConfigs[0].natIP)')INTERNAL_IP=$(gcloud compute instances describe ${instance}   --format 'value(networkInterfaces[0].networkIP)')cfssl gencert   -ca=ca.pem   -ca-key=ca-key.pem   -config=ca-config.json   -hostname=${instance},${EXTERNAL_IP},${INTERNAL_IP}   -profile=kubernetes   ${instance}-csr.json | cfssljson -bare ${instance}done
 
gcloud  compute --project=PROJECT_NAME instances create RedditPuma --zone=us-east1-b --machine-type=f1-micro --subnet=default --tags=puma-server --image=reddit-base --image-project=PROJECT_NAME --boot-disk-size=10GB --boot-disk-type=pd-standard
gcloud  compute --project=PROJECT_NAME instances create Reddit-Puma --zone=us-east1-b --machine-type=f1-micro --subnet=default --tags=puma-server --image=reddit-base --image-project=PROJECT_NAME --boot-disk-size=10GB --boot-disk-type=pd-standard
gcloud auth application-default login
gcloud auth list
gcloud auth login
gcloud beta compute --project=PROJECT_NAME instances create NAME --zone=us-east1-b --machine-type=f1-micro --subnet=default --tags=puma-server --image=reddit-base --image-project=PROJECT_NAME --boot-disk-size=10GB --boot-disk-type=pd-standard
gcloud beta container clusters update <standard-cluster-1 --zone=us-central1-a  --enable-network-policy
gcloud beta container clusters update standard-cluster-1 --zone=us-central1-a  --enable-network-policy
gcloud beta container clusters update standard-cluster-1 --zone=us-central1-a --update-addons=NetworkPolicy=ENABLED
gcloud components update
gcloud compute addresses create kubernetes-the-hard-way   --region $(gcloud config get-value compute/region)
gcloud compute addresses describe kubernetes-the-hard-way   --region $(gcloud config get-value compute/region)   --format 'value(address)'
gcloud compute addresses list --filter="name=('kubernetes-the-hard-way')"
gcloud compute disks create --size=25GB --zone=us-central1-a reddit-mongo-disk
gcloud compute firewall-rules create kubernetes-the-hard-way-allow-external   --allow tcp:22,tcp:6443,icmp   --network kubernetes-the-hard-way   --source-ranges 0.0.0.0/0
gcloud compute firewall-rules create kubernetes-the-hard-way-allow-internal   --allow tcp,udp,icmp   --network kubernetes-the-hard-way   --source-ranges 10.240.0.0/24,10.200.0.0/16
gcloud compute firewall-rules create kubernetes-the-hard-way-allow-nginx-service   --allow=tcp:${NODE_PORT}   --network kubernetes-the-hard-way
gcloud compute firewall-rules create prometheus-default --allow tcp:9090
gcloud compute firewall-rules create puma-default --allow tcp:9292 
gcloud compute firewall-rules create reddit-app   --allow tcp:9292   --target-tags=docker-machine   --description="Allow PUMA connections"   --direction=INGRESS 
gcloud compute firewall-rules create reddit-app  --allow tcp:9292  --target-tags=docker-machine  --description="Allow PUMA connections"  --direction=INGRESS 
gcloud compute firewall-rules list --filter="network:kubernetes-the-hard-way"
gcloud compute http-health-checks create kubernetes     --description "Kubernetes Health Check"     --host "kubernetes.default.svc.cluster.local"     --request-path "/healthz"  gcloud compute firewall-rules create kubernetes-the-hard-way-allow-health-check     --network kubernetes-the-hard-way     --source-ranges 209.85.152.0/22,209.85.204.0/22,35.191.0.0/16     --allow tcp  gcloud compute target-pools create kubernetes-target-pool     --http-health-check kubernetes  gcloud compute target-pools add-instances kubernetes-target-pool    --instances controller-0,controller-1,controller-2  gcloud compute forwarding-rules create kubernetes-forwarding-rule     --address ${KUBERNETES_PUBLIC_ADDRESS}     --ports 6443     --region $(gcloud config get-value compute/region)     --target-pool kubernetes-target-pool
gcloud compute instances create reddit-app   --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure  --metadata-from-file startup-script=startup-script.sh
gcloud compute instances create reddit-app   --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure \   --metadata-from-file startup-script=startup-script.sh
gcloud compute instances create reddit-app   --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure \ --metadata-from-file startup-script=startup-script.sh
gcloud compute instances create reddit-app   --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure   --metadata-from-file startup-script=startup-script.sh
gcloud compute instances create reddit-app   --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure   --metadata-from-file startup-script=startup_script.sh
gcloud compute instances create reddit-app  --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure
gcloud compute instances create reddit-app  --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure \   --metadata-from-file startup-script=startup_script.sh
gcloud compute instances create reddit-app  --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure \   --metadata-from-file startup-script=startup-script.sh
gcloud compute instances create reddit-app  --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure \   --startup-script=startup_script.sh
gcloud compute instances create reddit-app  --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure : 1539803311:0;ssh -i ~/.ssh/appuser appuser@35.228.143.155
gcloud compute instances create reddit-app2   --boot-disk-size=10GB   --image-family ubuntu-1604-lts   --image-project=ubuntu-os-cloud   --machine-type=g1-small   --tags puma-server   --restart-on-failure   --metadata-from-file startup-script=startup_script.sh
gcloud compute instances create
gcloud compute instances list
gcloud compute machine-types list --filter=zone:europe-west1-d
gcloud compute networks create kubernetes-the-hard-way --subnet-mode custom
gcloud compute networks subnets create kubernetes   --network kubernetes-the-hard-way   --range 10.240.0.0/24
gcloud compute --project=PROJECT_NAME firewall-rules create default-puma-server --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:9292 --source-ranges=0.0.0.0/0 --target-tags=puma-server
gcloud compute --project=PROJECT_NAME firewall-rules create NAME --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:9292 --source-ranges=0.0.0.0/0 --target-tags=puma-server
gcloud compute --project=PROJECT_NAME firewall-rules create NAME --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:9292 --source-ranges=0.0.0.0/0 --target-tags=puma-server --resource.name=test
gcloud compute --project=PROJECT_NAME instances create NAME --zone=us-east1-b --machine-type=f1-micro --subnet=default --tags=puma-server --image=reddit-base --image-project=PROJECT_NAME --boot-disk-size=10GB --boot-disk-type=pd-standard
gcloud compute --project=PROJECT_NAME instances create puma-service --zone=us-east1-b --machine-type=f1-micro --subnet=default --tags=puma-server --image=reddit-base --image-project=PROJECT_NAME --boot-disk-size=10GB --boot-disk-type=pd-standard
gcloud compute --project=PROJECT_NAME firewall-rules create kubernetes-nodeports --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:30000-32767 --source-ranges=0.0.0.0/0
gcloud compute routes list --filter "network: kubernetes-the-hard-way"
gcloud compute ssh ${INSTANCE_NAME}
gcloud compute ssh controller-0
gcloud compute ssh controller-0   --command "kubectl get nodes --kubeconfig admin.kubeconfig"
gcloud compute ssh controller-0   --command "sudo ETCDCTL_API=3 etcdctl get   --endpoints=https://127.0.0.1:2379   --cacert=/etc/etcd/ca.pem   --cert=/etc/etcd/kubernetes.pem   --key=/etc/etcd/kubernetes-key.pem  /registry/secrets/default/kubernetes-the-hard-way | hexdump -C"
gcloud compute ssh controller-0   --command "sudo ETCDCTL_API=3 etcdctl get   --endpoints=https://127.0.0.1:2379   --cacert=/etc/etcd/ca.pem   --cert=/etc/etcd/kubernetes.pem   --key=/etc/etcd/kubernetes-key.pem  /registry/secrets/default/kubernetes-the-hard-way "
gcloud compute ssh controller-1
gcloud compute ssh controller-1   --command "kubectl get nodes --kubeconfig admin.kubeconfig"
gcloud compute ssh controller-2
gcloud compute ssh worker-2
gcloud config 
gcloud config get-value 
gcloud config list 
gcloud config set project infra-2194
gcloud config set project list
gcloud container clusters get-credentials big-cluster --zone us-central1-a --project PROJECT_NAME
gcloud container clusters get-credentials new-cluster --zone us-west1-a --project PROJECT_NAME
gcloud container clusters get-credentials standard-cluster-1 --zone us-central1-a --project PROJECT_NAME
gcloud container clusters get-credentials standard-cluster-1 --zone us-central1-a --project PROJECT_NAME  && kubectl port-forward $(kubectl get pod --selector="app=reddit,component=ui,release=ui-1" --output jsonpath='{.items[0].metadata.name}') 8080:9292
gcloud info 
gcloud init
gcloud projects list 
gcloud versiob
gcloud version

gem
gem install travis
gem list
gem update --system

git add *
git add .
git add .gitignore README.md terraform/main.tf terraform/variables.tf
git apply
git branch ansible-1
git branch terraform-2
git checkout bff762fb14ff73d84f13d9f2bfe910526d06ea55
git checkout -f monitoring-2
git checkout terraform-2
git chekout master
git clone 
git clone git@github.com:Otus-DevOps-2018-09/USER_NAME09_infra.git
git clone git@gitlab.com:italian-server/server-deploy.git -key "~/.ssh/gitlab-com"
git clone https://github.com/powerline/fonts.git --depth=1

git commit --amend
git commit --help
git commit -m  'HW-23 (kubernetes-3)'
git diff
git diff packer-base
git -f push -u --all
git fetach
git fetch
git fetch origin
git g
git init
git lof
git log
git merge feature/3
git merge master
git merge --no-ff ansible-3
git mv cloud-bastion.ovpn vpn/
git mv lb.tf files/
git mv README.mc README.md
git mv README.new README.mc
git mv roles/app/files/puma.service roles/app/templates
git mv roles/app/files/puma.service roles/app/templates.puma.service
git mv setupvpn.sh vpn
git mv vpn VPN
git mv vpn VPN2
git plan
git pull
git pull gitlab
git pull gitlab gitlab-ci-1
git pull logging-1 logging-1
git pull origin master
git pull origin/logging-1 logging-1
git push
git push  --set-upstream origin ansible-2
git push -f
git push -f gitlab gitlab-ci-1
git push -f origin -u --all
git push -f --set-upstream origin ansible-1
git push gitlab2 gitlab-ci-2 --tags
git push --set-upstream origin terraform-2
git push -u -all 
git rebase 8dc460f60235fd3871bebc5c1e12bc662f579ce9
git rebase --abort
git rebase --continue
git rebase --edit-todo
git rebase -i HEAD~0
git rebase -i HEAD~1
git rebase -i HEAD~2
git remote add https://github.com/USER_NAME09/quick-golang.git
git remote add origin git@github.com:USER_NAME09/practice-git-1.git
git remote add origin git@github.com:USER_NAME09/practice-git-2.git
git remote add origin http://gitlab-gitlab/USER_NAME/post.git
git remote add origin https://github.com/USER_NAME09/quick-golang.git
git revert f166991d756edcfece873c9737909eedd4fc27c2
git rm ansible/roles/jdauphant.nginx/
git rm --cached docker/.env
git rm -f terraform/terraform.tfstate
git rm -r ansible/roles/jdauphant.nginx/
git show
git status 
git tag 
git tag 2.4.10
git tag -a Travis
git update-index --chmod=+x  install_*
git update-index --chmod=+x *.sh
git update-index --chmod=+x deploy.sh install_mongodb.sh install_ruby.sh startup_script.sh



google compute ssh controller-1
got status
hadolint

hadolint Dockerfile

head -c 32 /dev/urandom 

helm
helm 
helm del --purge gitlab
helm del --purge grafana
helm delete grafana
helm dep update ./reddit 
helm dep update --debug
helm describe test-ui-1
helm fetch  stable/prometheus
helm fetch gitlab/gitlab-omnibus --version 0.1.37 --untar 
helm fetch --untar stable/prometheus
helm init --service-account tiller 
helm inspect gitlab-gitlab-runner-5df57b8848-7x8l7
helm install grafana stable/grafana --set "adminPassword=admin"   --set "service.type=NodePort"   --set "ingress.enabled=true"   --set "ingress.hosts={reddit-grafana}"
helm install --name gitlab . -f values.yaml 
helm install prom . -f custom_values.yml 
helm install stable/nginx-ingress --name nginx
helm install ui --name ui-1
helm ls
helm repo add gitlab https://charts.gitlab.io 
helm search mongo
helm update  ui-2
helm update ui --name ui-2
helm upgrade <release-name> ./reddit 
helm upgrade --install grafana stable/grafana --set "adminPassword=admin"   --set "service.type=NodePort"   --set "ingress.enabled=true"   --set "ingress.hosts={reddit-grafana}"
helm upgrade --install grafana stable/grafana --set "adminPassword=admin" --set "service.type=NodePort" --set "ingress.enabled=true" --set "ingress.hosts={reddit-grafana}"
helm upgrade --install grafana stable/grafana --set "server.adminPassword=admin"   --set "server.service.type=NodePort"   --set "server.ingress.enabled=true"   --set "server.ingress.hosts={reddit-grafana}"
helm upgrade production --namespace production ./reddit --install
helm upgrade prom . -f custom_values.yml --install
helm upgrade reddit-test ./reddit
helm upgrade reddit-test ./reddit —install
helm upgrade staging --namespace staging ./reddit --install
helm upgrade ui-1 ui/ 

INSTANCE_NAME=$(kubectl get pod untrusted --output=jsonpath='{.spec.nodeName}')

kill $(ps aux | grep mdwork | grep spotlight | cut -f '9' -d ' ')

kubectl 
kubectl apply comment-deployment.yml
kubectl apply -f .
kubectl apply -f ./kubernetes/reddit/ -n dev
kubectl apply -f https://storage.googleapis.com/kubernetes-the-hard-way/coredns.yaml
kubectl apply -f kubernetes/reddit/tiller.yml
kubectl apply -f mongo-deployment.yml post-deployment.yml ui-deployment.yml
kubectl config current-context
kubectl config view
kubectl context 
kubectl create secret generic kubernetes-the-hard-way  --from-literal="mykey=mydata"
kubectl create secret tls ui-ingress --key tls.key --cert tls.crt -n dev
kubectl delete 
kubectl delete deploy mongo -n dev
kubectl delete deploy ui -n dev
kubectl delete deployments nginx-1
kubectl delete -f .
kubectl delete -f ui-ingress.yml -n dev
kubectl delete ingress ui -n dev
kubectl delete secret tls 
kubectl delete secret tls -n dev
kubectl delete secret tls ui-ingres -n dev
kubectl delete secret tls ui-ingress
kubectl delete secret tls ui-ingress --key tls.key --cert tls.crt -n dev
kubectl delete service nginx-1-service
kubectl delete service ui -n dev
kubectl delete ui-deployment.yml
kubectl describe
kubectl describe nodes
kubectl describe pod gitlab-gitlab-7696bc7dbd-pkz8l
kubectl describe pod ui-1-ui-658b6fcc8d-km6n7
kubectl describe secret ui-ingress -n dev
kubectl describe service ui | grep Endpoints
kubectl describe service ui -n dev | grep NodePort
kubectl describe storageclass standard -n dev 
kubectl exec -it grafana-bdc977fd4-lxscw bash
kubectl exec -it grafana-bdc977fd4-lxscw sh
kubectl exec -ti $POD_NAME -- nslookup busybox
kubectl exec -ti $POD_NAME -- nslookup kubernetes
kubectl exec -ti mongo-7f99d9bccc-5vf6n nslookup comment
kubectl exec -ti ui-84994b4554-5m4cb nslookup post
kubectl expose deployment nginx --port 80 --type NodePort
kubectl get componentstatuses
kubectl get deployment -n default
kubectl get deployments
kubectl get deployments -n dev
kubectl get ingres -n dev
kubectl get ingress
kubectl get ingress -n default
kubectl get ingress -n dev
kubectl get ingress -n dev 
kubectl get nodes -o wide 
kubectl get nodes
kubectl get persistentvolume -n dev
kubectl get po
kubectl get pod -n dev
kubectl get pods 
kubectl get pods -l k8s-app=kube-dns -n kube-system
kubectl get pods -l run=busybox 
kubectl get pods -l run=busybox -o jsonpath
kubectl get pods -l run=busybox -o jsonpath="{.items[0].metadata.age}"
kubectl get pods -l run=busybox -o jsonpath="{.items[0].metadata.name}"
kubectl get pods -l run=busybox -o jsonpath="{.items[0].metadata.status}"
kubectl get pods -l run=busybox
kubectl get pods -l run=nginx
kubectl get pods -n  kube-system 
kubectl get pods -n default
kubectl get pods -n dev
kubectl get pods -n kube-system --selector app=helm 
kubectl get pods -o wide
kubectl get pods --selector component=ui
kubectl get pods --selector component=uo
kubectl get service 
kubectl get service -n dev --selector component=ui
kubectl get service -n nginx-ingress nginx
kubectl get services
kubectl get services -n dev
kubectl get svc
kubectl insect gitlab-gitlab-runner-5df57b8848-7x8l7
kubectl inspect
kubectl inspect gitlab-gitlab-runner-5df57b8848-7x8l7
kubectl inspect pod gitlab-gitlab-runner-5df57b8848-7x8l7
kubectl log -f grafana-bdc977fd4-gpr5d
kubectl logs $POD_NAME
kubectl logs -f comment-559cc97f59-hnwsq -n dev
kubectl logs -f comment-559cc97f59-jk44f
kubectl logs -f post-57788c57f6-427cj
kubectl logs -f ui-84994b4554-5m4cb
kubectl logs reddit-test-ui-78664855d5-pvdpr
kubectl pod inspect gitlab-gitlab-runner-5df57b8848-7x8l7
kubectl port-forward $POD_NAME 8080:80
kubectl port-forward comment-757c84f994-5w47f 8080:9292
kubectl port-forward post-57788c57f6-8jw6s 5000:5000
kubectl port-forward ui-5d69f5784f-85scd 9292:9292
kubectl run busybox --image=busybox:1.28 --command -- sleep 3600
kubectl run nginx --image=nginx
kubectl scale deployment --replicas 0 -n kube-system kube-dns
kubectl scale deployment --replicas 0 -n kube-system kube-dnsautoscaler
kubectl service 

kubectl service delete nginx-1-service
kubectl su-exec -it grafana-bdc977fd4-lxscw bash
kubectl -v
kubectl version
kubectl --version
KUBERNETES_PUBLIC_ADDRESS=$(gcloud compute addresses describe kubernetes-the-hard-way   --region $(gcloud config get-value compute/region)   --format 'value(address)')
lsblk
lw

mdutil -E /

minikube
minikube addons enable
minikube addons enable dashboard
minikube addons list
minikube addons listkubectl get all -n kube-system--selector k8s-app=kubernetes-dashboard
minikube start
minikube stop

molecule 
molecule converge 
molecule create
molecule destroy
molecule init
molecule init scenario --scenario-name default -r db -d vagrant
molecule list
molecule verify
molecule --version 



NODE_PORT=$(kubectl get svc nginx   --output=jsonpath='{range .spec.ports[0]}{.nodePort}')
nslookup www.dragonknight.ru
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout tls.key -out tls.crt -subj "/CN=35.201.126.86"
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout tls.key -out tls.crt -subj "/CN=35.201.67.17"

packer
packer build  -var-file=variables.json immutable.json
packer build  -var-file=variables.json ubuntu16.json
packer build ./ubuntu16.json
packer build app.json
packer build db.json
packer build packer/app.json
packer build --var-file=variables.json ubuntu16.json
packer buils ./ubuntu16.json
packer validate  -var-file=variables.json.example ubuntu16.json
packer validate ./ubuntu16.json
packer version


pip install apache-libcloud
pip install molecule
pip install passlib
pip install testinfra
pip install --upgrade pip
pip install virtualenv
pip -v
pip --version
POD_NAME=$(kubectl get pods -l run=busybox -o jsonpath="{.items[0].metadata.name}")
POD_NAME=$(kubectl get pods -l run=nginx -o jsonpath="{.items[0].metadata.name}")
post
pip install ansible --quiet
pip install apache-libcloud
pip install passlib
pip install --upgrade pip
pip install virtualenv virtualenvwrapper
pip2 install ansible-lint



ruby --version
rubygems --version

screen
screen man
screen off

source $HOME/.profile
source --help
source pyenv/bin/activate
ssh-agent $(ssh-add /somewhere/yourkey; git clone git@github.com:user/project.git)
ssh-keygen
ssh-keygen -t rsa -f ~/.ssh/appuser -C appuser -P ""

ETCDCTL_API=3 etcdctl member list   --endpoints=https://127.0.0.1:2379   --cacert=/etc/etcd/ca.pem   --cert=/etc/etcd/kubernetes.pem   --key=/etc/etcd/kubernetes-key.pem

gem install travis
gem update --system
kill $(ps aux | grep mdwork | grep spotlight | cut -f '9' -d ' ')
mdutil -a -i off
mdutil -E /
mkdir /Volumes/Encrypted


terarform plan
terrafom show
terraform
terraform apply
terraform apply -auto-approve=false
terraform apply -auto-approve=false 
terraform destroy
terraform destroy -auto-approve 
terraform destroy --help
terraform fmt
terraform get
terraform import google_compute_firewall
terraform import google_compute_firewall.firewall_mongo
terraform init
terraform init -backend=false && terraform validate -var-file=terraform.tfvars.example
terraform output
terraform output app_external_ip
terraform plan
terraform play
terraform refresh
terraform show
terraform show | grep assigned_nat_ip
terraform taint google_compute_instance.app 
terraform update
terraform -v


travis encrypt "slack_namespace:TOKEN#channel_name" --add notifications.slack.rooms --pro -r Otus-DevOps-2018-09/USER_NAME09_microservices
travis login --com
travis token --com

tree ui

vagrant
vagrant box
vagrant box billryan/win-xp-sp3
vagrant box list
vagrant box remove hashicorp/precise64
vagrant destroy -f
vagrant list
vagrant provision appserver 
vagrant provision dbserver
vagrant ssh appserver
vagrant status
vagrant up

virtualenv
virtualenv pyenv
virtualenv testing
virtualenv --version

wget --help
wget https://github.com/express42/reddit/archive/microservices.zip
wget https://raw.githubusercontent.com/express42/otus-snippets/master/hw-04/PULL_REQUEST_TEMPLATE.md -O PULL_REQUEST_TEMPLATE.md
```