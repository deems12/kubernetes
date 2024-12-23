mkdir ro
cd ro
echo .>app.py
code .
echo .>dockerfile
code .
echo .>requirements.txt
code .
docker build -t dheemanth21/flask-api:latest .
docker login
docker push dheemanth21/flask-api:latest .
echo .>deployment.yaml
code .
echo .>service.yaml
code .
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl get pods 
curl http://localhost:3002/ .# kubernetes
