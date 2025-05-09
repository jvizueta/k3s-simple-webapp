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

