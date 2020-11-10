# react-eacf-app
A Single Page react app for EACF (Evangelical Alliance Christian Fellowship)

1. Build optimised npm packages
```bash
npm run-script build
```
2. Create Dockerfile file
```
FROM nginx:1.19.0
COPY build/ /usr/share/nginx/html
```

3. Create .dockerignore to prevent copying large node_modules folder into image

4. Push image to local docker registry
```bash
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

5. Build and tag the image for pushing to docker hub registry
```bash
docker build -t tic-tac-toe .
docker tag tic-tac-toe andeslam2019/tic-tac-toe:latest
docker push andeslam2019/tic-tac-toe:latest
```

6. Deploy this new image in k8s
kubectl apply -f deploy.yml


## Deploy to aws
1.  export KUBECONFIG=~/.kube/eks-andes
