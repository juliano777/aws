# Contêineres

Amazon ECS (Elastic Container Service) e Amazon EKS (Elastic Kubernetes
Service) são serviços da AWS para gerenciamento e orquestração de
contêineres. Porem eles têm diferenças importantes que serão vistas a seguir.

## Amazon ECS (Elastic Container Service)

É o serviço da AWS para gerenciar contêineres Docker, cujo modelo de
gerenciamento é proprietário da AWS.  
Utiliza orquestração nativa, proprietária da AWS.  
Tem forte integração com outros serviços como IAM, CloudWatch, ALB, etc.  
Em termos de complexidade é mais simples do que configurar o Kubernetes.  
Como casos de uso podem ser citadas aplicações que não exigem portabilidade
entre _clouds_ ou uso de padrões Kubernetes.

Formas de execução:
 - **ECS Launch Type**: gerenciamento das dinstâncias feito pelo usuário;
 - **Fargate Launch Type**: execução _serverless_, sem se preocupar com servidores.
  
## EKS (Elastic Kubernetes Service)

É o serviço gernciado de Kubernetes na AWS, cujo modelo de gerenciamento é
baseado no Kubernetes padrão da [CNCF](https://www.cncf.io/).  
Orquestração Kubernetes com total compatibilidade com suas APIs e
ferramentas.  
Também tem integração com serviços da AWS, porém mais complexa.  
Sua complexidade pode ser descrita como maior curva de aprendizado, pois é
necessário prévio conhecimento de Kubernetes.  
Casos de uso: ao precisar de portabilidade entre _clouds_ ou já usa Kubernetes
_on-premises_.

Formas de execução:
 - **EC2**: gerenciamento dos nós feito pelo usuário;
 - **Fargate**: execução _serverless_ para pods.


## Principais diferenças

| Aspecto                  | Amazon ECS                              | Amazon EKS                                 |
|---------------------------|----------------------------------------|-------------------------------------------|
| **Orquestrador**         | Proprietário da AWS                   | Kubernetes (padrão CNCF)                 |
| **Curva de Aprendizado** | Baixa                                 | Alta                                      |
| **Portabilidade**        | Baixa                                 | Alta (multi-cloud, on-premises)          |
| **Integração AWS**       | Muito forte                           | Boa, mas exige configuração adicional     |
| **Modelo de Execução**   | EC2 ou Fargate                        | EC2 ou Fargate                            |
| **Escalabilidade**       | Automática com Service Auto Scaling   | Alta, com HPA, Cluster Autoscaler        |
| **Resiliência**          | Boa, depende do design do serviço     | Muito alta, com múltiplos control planes  |
| **Custo**                | Geralmente menor                      | Geralmente maior (mais componentes)       |
| **Complexidade**         | Simples de gerenciar                  | Complexo (clusters, nós, control plane)   |
| **Casos de Uso**         | Aplicações AWS nativas, simplicidade  | Workloads Kubernetes, portabilidade       |