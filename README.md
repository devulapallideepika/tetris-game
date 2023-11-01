
## Deploying tetris-game on eks using Argocd
- create ec2 instance and iam role with permissions-
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/74c4bfd3-40f0-4807-ae4f-885acf690060)
- install awscli
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/88da2a8d-8c70-409f-9f4b-584fe5cd8c32)  
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/42475960-0c0d-4354-876b-78c0da1fd0c3)
- install kubectl
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/ce406600-be4b-429a-9d00-168f06936667)
- install eksctl
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/759792c2-ed59-4ddc-9976-e74c797c9416)
- create eksctl cluster
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/b9d4f125-3af7-47b6-ba90-e46c4a55bc60)
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/65801fce-f117-4acb-b6c1-8515634b7c53)
- install argocd using commands
- $ kubectl create namespace argocd
- $ kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
- $ kubectl get pods -n argocd
- $ curl --silent --location -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/download/v2.4.7/argocd-linux-amd64
- $ chmod +x /usr/local/bin/argocd
- $ kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
- $ kubectl get svc -n argocd
- $ kubectl get secret argocd-initial-admin-secret -n argocd -o yaml -to get password
- $ echo XXXXXXX | base64 --decode -to decode the password

![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/2e8b8899-0ed9-491a-bb43-1d2b8ddee8c5)
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/670b8349-8150-4cd1-bef4-10d74ea3f220)

![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/9d55029d-116d-4d43-975a-5ccd73ca58ca)
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/7feac492-3ad5-4fc0-b008-05d65a958f91)
- Access the tetris-game using loadbalancer.
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/61aca84c-7804-4b19-ae28-f31e97ce7679)
![image](https://github.com/devulapallideepika/tetris-game/assets/129947829/af3dd3f1-36fa-4299-8237-b294e387216e)
