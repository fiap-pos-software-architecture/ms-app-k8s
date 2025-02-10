# MS-APP-K8S

Este repositório contém os arquivos de configuração para a implantação do microserviço **hackaton-ms-app** em um cluster Kubernetes.

## 📁 Estrutura do Repositório

```
MS-APP-K8S
│── kubernetes/
│   ├── App/
│   │   ├── app-configmap.yaml
│   │   ├── app-deployment.yaml
│   │   ├── app-hpa.yaml
│   │   ├── app-service.yaml
│   │   ├── components.yaml
```

- **`app-configmap.yaml`**: Configurações da aplicação armazenadas como ConfigMap.
- **`app-deployment.yaml`**: Manifesto para implantação da aplicação.
- **`app-hpa.yaml`**: Configuração de escalabilidade automática com Horizontal Pod Autoscaler (HPA).
- **`app-service.yaml`**: Serviço Kubernetes para expor a aplicação internamente ou externamente.
- **`components.yaml`**: Definição adicional de componentes, se necessário.

## 🚀 Implantação no Kubernetes

### 1️⃣ Pré-requisitos

- **Docker** e **kubectl** instalados.
- Kubernetes configurado (pode ser minikube, kind, EKS, GKE, etc.).

### 2️⃣ Aplicando os recursos no cluster

Para implantar a aplicação, execute os seguintes comandos:

```bash
kubectl apply -f kubernetes/App/app-configmap.yaml
kubectl apply -f kubernetes/App/app-deployment.yaml
kubectl apply -f kubernetes/App/app-hpa.yaml
kubectl apply -f kubernetes/App/app-service.yaml
kubectl apply -f kubernetes/App/components.yaml
```

### 3️⃣ Verificando a implantação

Após a execução dos comandos acima, você pode verificar se os recursos foram criados corretamente com:

```bash
kubectl get pods
kubectl get services
kubectl get deployments
kubectl get hpa
```

### 4️⃣ Acessando a aplicação

Caso a aplicação esteja exposta como um **LoadBalancer** ou **NodePort**, obtenha o IP externo com:

```bash
kubectl get svc
```

Acesse a aplicação via navegador ou ferramenta como `curl`:

```bash
curl http://<EXTERNAL-IP>:<PORT>
```

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

---
