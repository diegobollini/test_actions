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

- Github settings
Repositorio > Settings > Secrets > New
DOCKER_USERNAME = diegobollini  
DOCKER_PASSWORD = "pass"

