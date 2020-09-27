# k3s Install

curl https://releases.rancher.com/install-docker/19.03.sh | sh

curl -sfL https://get.k3s.io | sh -s - --docker --disable traefik --disable servicelb

/var/lib/rancher/k3s/server/node-token

curl -sfL https://get.k3s.io | K3S_URL=https://192.168.1.151:6443 K3S_TOKEN=K10208f6202b873294d607c78b4c4f6f92b2fde3b288339d485fb393aab9fd57376::server:5773b2a19293211e5ddc8adc86fa29f2 sh -s - --docker --disable traefik --disable servicelb

# Metallb

helm install rpi-metallb --create-namespace --namespace rpi-controlplane metallb
helm upgrade rpi-metallb --create-namespace --namespace rpi-controlplane metallb


# Nginx Ingress controller

helm install rpi-nginx-ingress --create-namespace --namespace rpi-controlplane nginx-ingress
helm upgrade rpi-nginx-ingress --create-namespace --namespace rpi-controlplane nginx-ingress


# Prometheus Operator

helm install rpi-prometheus --create-namespace --namespace rpi-controlplane prometheus-operator
helm upgrade rpi-prometheus --create-namespace --namespace rpi-controlplane prometheus-operator

# Cert Manager

helm install rpi-cert-manager --create-namespace --namespace rpi-controlplane cert-manager
helm upgrade rpi-cert-manager --create-namespace --namespace rpi-controlplane cert-manager

helm install rpi-cm-ca-issuer --create-namespace --namespace rpi-controlplane cm-ca-issuer
helm upgrade rpi-cm-ca-issuer --create-namespace --namespace rpi-controlplane cm-ca-issuer

# Pi-Hole

helm install rpi-hole --create-namespace --namespace rpi-controlplane pi-hole
helm upgrade rpi-hole --create-namespace --namespace rpi-controlplane pi-hole

# oauth2 proxy

helm install rpi-oauth2-proxy --create-namespace --namespace rpi-controlplane oauth2-proxy
helm upgrade rpi-oauth2-proxy --create-namespace --namespace rpi-controlplane oauth2-proxy

# Hadoop

helm install rpi-hadoop --create-namespace --namespace rpi-hadoop hadoop
helm upgrade rpi-hadoop --create-namespace --namespace rpi-hadoop hadoop

# jupyterhub

helm install rpi-jupyterhub --create-namespace --namespace rpi-jupyterhub jupyterhub/
helm upgrade rpi-jupyterhub --create-namespace --namespace rpi-jupyterhub jupyterhub/

# hue

helm install rpi-hue --create-namespace --namespace rpi-hue hue/
helm upgrade rpi-hue --create-namespace --namespace rpi-hue hue/

# elasticsearch

helm install rpi-elasticsearch --create-namespace --namespace rpi-elasticsearch elasticsearch/
helm upgrade rpi-elasticsearch --create-namespace --namespace rpi-elasticsearch elasticsearch/

# mongodb

helm install rpi-mongodb --create-namespace --namespace rpi-mongodb mongodb/
helm upgrade rpi-mongodb --create-namespace --namespace rpi-mongodb mongodb/

# kafka

helm install rpi-kafka --create-namespace --namespace rpi-kafka kafka/
helm upgrade rpi-kafka --create-namespace --namespace rpi-kafka kafka/

# zookeeper

helm install rpi-zookeeper --create-namespace --namespace rpi-zookeeper zookeeper/
helm upgrade rpi-zookeeper --create-namespace --namespace rpi-zookeeper zookeeper/

helm install rpi-spark--create-namespace --namespace rpi-spark spark/
helm upgrade rpi-spark --create-namespace --namespace rpi-spark spark/
