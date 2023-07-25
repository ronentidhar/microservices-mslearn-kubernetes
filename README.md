https://learn.microsoft.com/en-us/training/modules/dotnet-deploy-microservices-kubernetes

docker-compose build
docker-compose up
http://localhost:5902

docker tag pizzafrontend td/pizzafrontend
docker tag pizzabackend td/pizzabackend

docker push td/pizzafrontend
docker push td/pizzabackend

kubectl apply -f backend-deploy.yml
kubectl apply -f frontend-deploy.yml

kubectl scale --replicas=5 deployment/pizzabackend

skaffold dev --port-forward
