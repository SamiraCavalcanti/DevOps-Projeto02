# 🚀 Projeto DevOps Fase 1: Website Containerizado na AWS

## 📋 Sobre o Projeto

Este é o **Projeto 02 - Fase 1** da minha jornada DevOps, demonstrando a implementação completa de containerização e deploy manual de uma aplicação web na AWS. O objetivo foi aplicar conceitos fundamentais de DevOps, Docker e computação em nuvem.

### 🎯 Roadmap das 3 Fases

- **✅ Fase 1** - O básico: Containerize e deploy manual de um site estático na AWS
- **🔄 Fase 2** - Adicione automação de infraestrutura com Terraform (IaC)  
- **🚀 Fase 3** - Full automation com CI/CD usando GitHub Actions + Terraform + Docker

> **Status atual**: Completando Fase 1 - Deploy manual com Docker + ECR + EC2

## 🛠️ Tecnologias Utilizadas

- **Docker** - Containerização da aplicação
- **Amazon ECR** - Registry de imagens Docker
- **Amazon EC2** - Hospedagem da aplicação
- **Nginx** - Servidor web
- **AWS CLI** - Automação e gerenciamento
- **IAM Roles** - Segurança e permissões

## 🏗️ Arquitetura

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Código Local   │────▶│   Docker Image  │────▶│    Amazon ECR   │
│  (HTML/CSS/JS)  │     │   (Container)   │     │   (Registry)    │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                                          │
                                                          ▼
                        ┌─────────────────┐     ┌─────────────────┐
                        │    Browser      │◀────│    Amazon EC2   │
                        │  (User Access)  │     │   (Container)   │
                        └─────────────────┘     └─────────────────┘
```

## 📦 Estrutura do Projeto

```
DevOps-Projeto02/
├── projeto-devops-fase-1/       # ✅ Fase 1: Deploy Manual (ATUAL)
│   ├── website/                 # Aplicação web estática
│   │   ├── index.html          # Página principal
│   │   ├── css/style.css       # Estilos
│   │   └── js/script.js        # Scripts
│   ├── Dockerfile              # Configuração do container
│   ├── imagens/                # Screenshots do projeto
│   └── README.md               # Documentação desta fase
├── projeto-devops-fase-2/       # 🔄 Fase 2: Terraform (IaC) 
│   └── (em desenvolvimento)
└── projeto-devops-fase-3/       # 🚀 Fase 3: CI/CD Completo
    └── (planejamento futuro)
```

## 🖼️ Demonstração

### 🎯 Aplicação em Produção
![Site funcionando na AWS](./imagens/Captura%20de%20tela%20de%202025-08-19%2020-08-22.png)

### 🐳 Container Registry (ECR)
![ECR Repository](./imagens/Captura%20de%20tela%20de%202025-08-19%2020-04-03.png)

### ☁️ Infraestrutura AWS
![EC2 Dashboard](./imagens/Captura%20de%20tela%20de%202025-08-19%2020-05-22.png)

### 💻 Container em Execução
![Container na EC2](./imagens/Captura%20de%20tela%20de%202025-08-19%2020-29-16.png)

---


## 🚀 Como Executar

### Pré-requisitos
- Docker instalado
- AWS CLI configurado
- Conta AWS ativa

### 1. Clone o repositório
```bash
git clone https://github.com/SamiraCavalcanti/DevOps-Projeto02.git
cd DevOps-Projeto02/projeto-devops-fase-1
```

### 2. Build da imagem Docker
```bash
docker build -t meu-site:v1.0 .
```

### 3. Teste local
```bash
docker run -d -p 8080:80 meu-site:v1.0
```

### 4. Deploy na AWS
```bash
# Login no ECR
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin [ACCOUNT-ID].dkr.ecr.us-east-1.amazonaws.com

# Tag e push da imagem
docker tag meu-site:v1.0 [ACCOUNT-ID].dkr.ecr.us-east-1.amazonaws.com/site-prod:v1.0
docker push [ACCOUNT-ID].dkr.ecr.us-east-1.amazonaws.com/site-prod:v1.0

# Deploy na EC2
ssh -i sua-chave.pem ec2-user@[EC2-IP]
docker pull [ACCOUNT-ID].dkr.ecr.us-east-1.amazonaws.com/site-prod:v1.0
docker run -d -p 80:80 [ACCOUNT-ID].dkr.ecr.us-east-1.amazonaws.com/site-prod:v1.0
```

## ✅ Resultados Alcançados

- ✅ **Containerização** completa da aplicação
- ✅ **Deploy automatizado** na AWS
- ✅ **Registry privado** configurado (ECR)
- ✅ **Infraestrutura** provisionada e configurada
- ✅ **Segurança** implementada com IAM Roles
- ✅ **Monitoramento** e logs configurados

## 🎯 Aprendizados

Durante este projeto, desenvolvi competências em:

- **Containerização** com Docker
- **Orquestração** de serviços AWS
- **Automação** de deploy
- **Segurança** em nuvem
- **Monitoramento** de aplicações
- **Boas práticas** DevOps

## � Roadmap de Evolução

### 📍 Fase 1 (Atual) - Deploy Manual ✅
- ✅ Containerização com Docker
- ✅ Registry privado (ECR)
- ✅ Deploy manual na EC2
- ✅ Configuração de segurança (IAM)

### 🎯 Fase 2 - Infrastructure as Code
- 🔄 Terraform para provisionamento automático
- 🔄 Versionamento de infraestrutura
- 🔄 Ambientes múltiplos (dev/prod)
- 🔄 Estado remoto do Terraform

### 🚀 Fase 3 - CI/CD Completo
- 🚀 GitHub Actions workflows
- 🚀 Deploy automático por push
- 🚀 Testes automatizados
- 🚀 Rollback automático
- 🚀 Monitoramento e alertas

---

## �🔗 Links Úteis

- [Docker Documentation](https://docs.docker.com/)
- [AWS ECR Guide](https://docs.aws.amazon.com/ecr/)
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [Terraform AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/)

## 👩‍💻 Contato

**Samira Cavalcanti** 
- GitHub: [@SamiraCavalcanti](https://github.com/SamiraCavalcanti)
- LinkedIn: [https://www.linkedin.com/in/samiracavalcanti/]

---

⭐ Se este projeto foi útil, deixe uma estrela!
