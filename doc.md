
docker run --name wordpress --network wordpress -d wordpress

docker run --name some-wordpress -p 8080:80 -d wordpress

docker build . -t wordpress:2-world

pwd/wordpress
├── Dockerfile
├── 

wordpress
├── Dockerfile
├── common.sh
├── entrypoint.sh
├── custom-theme
    ├──
├── custom-plugin
    ├──

docker build . -f wordpress/Dockerfile -t wordpress:2-world

cd wordpress
docker build . -t wordpress:2-world
docker run --name wordpress -p 8080:80 -d wordpress:2-world

docker compose up

kubectl apply -f pod.yaml
kubectl delete -f pod.yaml