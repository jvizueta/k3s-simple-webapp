# k3s-simple-webapp

Step 1.- Move to folder webapp
```
cd webapp
```

Step 2.- Login to your docker hub account
```
docker login
```

Step 3: Build the docker image and push it to your docker hub image registry
```
docker build -t youruser/nginx-webapp .
docker push youruser/nginx-webapp
```

Step 4: Deploy it in k3s
```
sudo k3s kubectl apply -f deployment.yaml
sudo k3s kubectl apply -f service.yaml
```

Step 5: view the webapp service
```
sudo k3s kubectl get svc webapp-service
```

Step 6: Access it from your web browser:
```
http://<NODE-IP>:<NODEPORT>
```

Troubleshooting: If you don't login to your docker hub account, the pods will show up as ImagePullBackOff when you run the following:

```
$ sudo k3s kubectl get pods
NAME                      READY   STATUS             RESTARTS   AGE
webapp-5655bb6994-fbgqc   0/1     ImagePullBackOff   0          8m24s
webapp-5655bb6994-s4nw8   0/1     ImagePullBackOff   0          8m24s
```
