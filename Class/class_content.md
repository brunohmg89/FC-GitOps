# FC-GitOps

Repositório criado para inserção de conteúdo do curso da FullCyle sobre Gitops

## Conceitos básicos

1. Introdução

2. Relembrando fluxo tradicional

 - Explicando fluxo de entrada de uma aplicação

 - Codigo fonte -> Repo GH -> CI -> CD -> K8S

3. Como o GitOps funciona

 - Continuação da explicação do fluxo de entrega

## Na prática

1. O que vamos fazer

 - Explicação do que iremos precisar e o que iremos fazer

2. Criando Webserver

 - Criando o arquivo `go.mod` com o comando `go mod init webserverfc`

 - Criando o arquivo `main.go` fazendo a criação de um Webserver

3. Criando imagem Docker

 - Criando o arquivo `Dockerfile`

4. Criando fluxo de geração de imagem

 - criando o arquivo `cd.yaml` dentro do diretório `.github\workflows`

5. Criando e configurando repositório

 - Criando as secrets dentro do repositório Git

 - Para senha do Dockerhub é necessário criar um `access token` dentro do dockerhub indo em "Accounting Settings -> Security -> New Access Token" após isso o resultado inserir dentro da secret do repositório.

 - A action `checkout@v2` está depreciada, código atualizado para a versão `checkout@v3`

 - Debugado código, estava apresentando erro, consertado linha do repositório, colocado USERNAME.

6. Criando manifesto Kubernetes

 - Criação dos arquivos de manifesto do Kubernetes, `deployment.yaml` e `service.yaml`

7. Iniciando com o Kustomize

 - Explicando sobre o Kustomize

 - Instalando o Kustomize via `choco install kustomize`

 - Criação do arquivo `kustomization.yaml` para a customização da imagem

8. Criando fluxo de CD

 - Configurando o Kustomize dentro do Workflow

 - Atualizando a TAG da imagem

 - Realizando commit com a TAG

 - Realizando o push para o repositório

9. Finalizando o fluxo de CD

 - Problema com o token, acertando o arquivo

 - Aplicando configurações no k8s `kubectl apply -f /k8s/

 - Github realizando a atualizando a TAG automaticamente

10. Instalando o ArgoCD

 - Getting Starterd ArgoCD <https://argo-cd.readthedocs.io/en/stable/getting_started/>

 - Passo 1 -> Install ArgoCD

 - Passo 2 -> Login Using The CLI (Para capturar a senha de admin), foi necessário instalar o base64 fiz via chocolatey.

 - Passo 3 -> Port Forwarding (Para publicar o ArgoCD em localhost)

11. Fazendo deploy com ArgoCD

 - Criando aplicação dentro do ArgoCD

 - Realizando Sync dentro do ArgoCD para verificar a saúde do Cluster

 - Tive um problema com o variável SHA dentro do workflow, faltava o `$`.

 - Atualizando o `main.go` para ver o deploy em andamento.

12. Fazendo Rollback e visualizando apps

 - É possível efetuar o rollback indo em `HISTORY AND ROLLBACK`

 - Algumas explicações do ArgoCD e como utiliza-lo

13. Últimas dicas

 - Dicas de conexão com repositórios privados indo em `Settings > Repositories`