# Github Actions - CI/CD Gratuito y fácil en Github

[Fuente: PeladoNerd](https://youtu.be/MNBf-ylhtK0)

## Create a new repository & clone:
```bash
$ git clone git@github.com:diegobollini/test_actions.git
$ ls
Dockerfile  index.html  README.md
```
## Create & configure actions
```bash
$ mkdir -p .github/workflow
$ nano .github/workflow/push.yml
```

## Secrets Github settings
Repositorio > Settings > Secrets > New
DOCKER_USERNAME = diegobollini  
DOCKER_PASSWORD = "pass"

## commit & deploy
Eliminé comentarios (#comentarios) de push.yml porque no funcionó el push > action.
Corregido y hecho el commit:
![image](https://i.imgur.com/W2XnqOS.png "deploy action")

## dockerhub
[Imagen](https://hub.docker.com/repository/docker/diegobollini/test_actions)
![image](https://i.imgur.com/B3Cengf.png "tags")

## github pages
Settings > GitHub Pages > Source
URL: https://diegobollini.github.io/test_actions/

## kubernetes con github
[Marketplace](https://github.com/marketplace?type=actions) > Types > Actions: kubectl  
[Github Action for Kubernetes CLI](https://github.com/marketplace/actions/kubernetes-cli-kubectl)  
Agregar action a push.yml y configurar según doc:  
KUBE_CONFIG_DATA – required: A base64-encoded kubeconfig file with credentials for Kubernetes to access the cluster. You can get it by running the following command:
```bash
cat $HOME/.kube/config | base64
```

### Linode: Create a Cluster
- label: testactions
- ver: 1.15
- Add Node Pools
- testactions-kubeconfig.yaml
```bash
$ cat ~/_desarrollo/test_actions/testactions-kubeconfig.yaml | base64 pbcopy
Secrets / New secret > KUBE_CONFIG_DATA
```
- commit & push