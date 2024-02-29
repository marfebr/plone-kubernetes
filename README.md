# Plonn em kuernetes com hpa

  Plone 6 em kubernetes
  essa é a forma mais estavel que encontrei para rodar o plone 6 em kubernetes

## Pré-requisitos

 * ter um fqdn:
   no caso estamos usando plone.hostlocal que foi defino no arquivo hosts da maquina local, mas emprodução deve ter uma entrada de DNS.
 * Ter um cluster Kubernetes funcionando com o ingress NGINX[https://kubernetes.github.io/ingress-nginx/deploy/]


## Os arquivos

  Os arquivos estão organizados da seguinte forma:

    1 - namespace.yaml: Cria o namespace para o projeto
    2 - configmaps.yaml: Variaveis de configuração Não sensivéis - para dados sensiveis use secrets
    3 - deployment.yaml - Declaração do frontend e backend
    4 - ingress.yaml - Regras para ingress para aplicação
    5 - services.yaml - Serviços do frontend e backend

  
  O namespace deve ser criado primeiro e na sequencia os demais

  ```bash

  kubectl apply -f namespace.yaml
  kubectl apply -f .
  ```
